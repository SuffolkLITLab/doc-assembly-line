# Names of internal objects

## Names for people

This list is very similar to the [list available here](https://github.com/SuffolkLITLab/doc-assembly-line/blob/master/labeling-pdf-fields.md#information-about-people).

One major difference: plural rather than singular variable names. Why? in a PDF file, it's tricky to use `array` syntax. So instead, we append a number to the end of the variable name to represent the first/second/third/etc. In a Docx template, we don't have that limit.

1. `users`
1. `other_parties`
1. `plaintiffs`
1. `defendants`
1. `petitioners`
1. `respondents`
1. `spouses`
1. `children`
1. `parents`
1. `guardians`
1. `caregivers`
1. `guardians_ad_litem`
1. `attorneys`
1. `translators`
1. `witnesses`
1. `debt_collectors`
1. `creditors`

To access the _first_ user in the list, use the syntax `users[0]`. You can access attributes of the `users[0]` like this: `users[0].attribute_name`. This is the same approach for each of the other lists.

## Attributes and methods that go along with people

### Special MAVirtualCourt methods and attributes
Docassemble has the built-in [`Individual`](https://docassemble.org/docs/objects.html#Individual) class.
The MAVirtualCourt project adds a few attributes and methods via the `VCIndividual` class.

* VCIndividual.`previous_addresses` is an object of type `AddressList`.
* `phone_numbers()` prints out a formatted list of phone numbers, labeled as `(cell)` or `(other)`

`PeopleList` is a list of VCIndividuals, with the special methods

* `names_and_addresses_on_one_line()`
* `familiar()` prints out the first name of each person in the list, using the function `comma_and_list`.
* `familiar_or()` prints out the first name of each person in the list, using the function `comma_and_list` but replacing the word "and" with the word "or" before the last person in the list.

These are not quite built-in attributes, but `basic-questions.yml` will provide definitions for these:

* `users[0].gender_female` is True if `user.gender` is female, and False otherwise (also for `users[1]`, `defendants[9]`, etc.)
* `users[0].gender_male` is True if `user.gender` is male, and False otherwise
* `users[0].gender_other` is True if `user.gender` is any value other than male or female.
* `users[0].signature` will prompt for the user's signature

### Built-in attributes

Here is a summary of some of the useful methods and attributes of an [`Individual`](https://docassemble.org/docs/objects.html#Individual), gathered together. Note some of these
are attributes that are actually objects, and thus documented in different sections of the Docassemble documentation.

* `name.first`, `name.middle`, `name.last`, and `name.suffix`
* `birthdate`
* `phone_number`
* `mobile_number`
* `gender`
* `address.address` (Street address), `address.unit`, `address.city`, `address.state`, `address.zip` and other attributes of an `Address` object.

## Other special variables

* `courts` is a list of MACourt objects. You will almost always only use `courts[0]`.
* `courts[0]` will print out the full name of the court, e.g., `Brighton Division, Boston Municipal Court`
* `courts[0].name` will also print out the full name of the court.
* `courts[0].department`
* `courts[0].division`
* `courts[0].phone`
* `courts[0].fax`
* `courts[0].location.latitude`
* `courts[0].location.longitude`
* `courts[0].has_po_box`
* `courts[0].description`
* `courts[0].address`, which includes `courts[0].address.county`

* `docket_numbers` a list of strings
* `signature_date`

## Variables that need to be defined if you are building an interview from scratch to deliver to the court

* `basic_questions_intro_screen` is the first variable you should list in your mandatory interview order control block
* `user_role` is an optional variable. You can define it to "plaintiff" or "defendant" if you know in advance which role the user will have
* `allowed_courts` is a list of court names. See below for a list of all possible values:
```
code: |
  allowed_courts = [
      "Boston Municipal Court",
      "District Court",
      "Superior Court",
      "Housing Court",
      "Probate and Family Court",
      "Juvenile Court",
      "Land Court",
      ]
```
* `preferred_court` is an optional variable (unusued until we get approval for final court selector). It can be set to the name of ONE of the available trial court departments.
* `final_form_to_file`: this variable should represent the final attachment as a PDF.
* `form_to_sign`: this variable should represent the final attachment as a PDF, without a signature.

### Customizing whether there is one/many or no items in a list

Sometimes you may want to avoid the "are there any" question. For example: if there is always at least one opposing party.

```
code: |
  # set the number of other parties to exactly one
  other_parties.there_are_any = True
  other_parties.there_is_another = False
```

If the docket number is never known in advance:

```
code: |
  docket_numbers[0] = ''
  docket_numbers.auto_gather = False
  docket_numbers.gathered = True
```  

### How to make a signature block optional in a Docx template

Version with only one person signing:

```
{%p if defined('users[0].signature') %}
{{ users[0].signature }}	
{%p endif %}
```

Version for multiple signers:
```
{%p if defined('users[0].signature') %}
{%p for user in users %}
{{ user.signature }}
{%p endfor %}
{%p endif %}
```

### Variables used for sending files to court

The below all need to be PDFs. Generally, do this in code. But if you have an interview with only
one PDF, you can use these variable names directly.

* form_to_file_no_cover
* form_to_sign (optional--only for preview screen)
* final_form_to_file: the basic-questions file automatically combines form_to_file_no_cover with the cover page to create this. Normally never need to deal with this variable at all.


These variables can all be created automatically for you by the basic-questions file, but you may not like those results. Make
the first two manually for most interviews.

### Review screen

* review_all_sections

We have a button by default on download/signature pages that refers to "review_all_sections" event.

You can make this a review screen for your form. If you don't, it will be a list of all of the navigation sections for your form.

```yaml
---
event: review_all_sections
question: |
  Review of your answers
subquestion: |
  
  ${showifdef('form_to_sign')}

  % if defined('form_delivery_complete'):
  **Warning: your form has already been delivered.** Any changes you make
  will _not_ be sent to the court.

  % endif
  Click a section to revisit the answers from that section.

  % for section in section_links(nav):
  * ${section}
  % endfor
  
  Press "${word("Resume")}" to resume the
  interview.
buttons:
  ${word("Resume")}: continue
```


### Preview and Final Download Screen with Send to Court buttons
```yaml
---
id: review before signature
need: form_to_sign
continue button field: [PLACEHOLDER: PREVIEW SCREEN VARIABLE]
question: |
  Nearly finished
subquestion: |
  You are almost done! Please click on the form below. It will open in a new window so you 
  can review it and make sure it is correct.
  
  Don't forget to come back to this page to click to the final step of signing and sending 
  the form to the court. 
  
   ${form_to_sign }

progress: 95
---
id: download form
event: download
comment: |
  The attachment email screen relies on final_form_to_file being defined. This
  will be built from the interview_metadata dictionary's contents, but if you
  add any addenda you will want to set this in a code block somewhere that takes
  priority over basic-questions.yml.
decoration: file-download
question: |
  % if not defined('email_success') or not email_success:
  Review, Download, and Send Form
  % else:
  Form delivered
  % endif
subquestion: |
  % if not defined('email_success') or not email_success:
  Thank you ${users[0]}. Your form is ready to send to the court. **It is not
  delivered until you complete the delivery process below.**

  1. Click the preview image below to open the form in a new window. Correct any errors using the "Make changes" button below.
  1. Download and save or print a copy of this form for your 
  records.
  1. Click the "Submit to ${courts[0]}" button to send it to the court. 
  1. You will have a chance to add instructions to the clerk and see the cover page before final delivery.
  % else:
  If you do not hear from the court in 1 business day, call the Trial Court’s
  Emergency HelpLine 833-91-COURT (833-912-6878).
  
  The Emergency HelpLine is open:  
  8:30am - 4:30pm,   
  Monday - Friday.
  % endif
  
  ${ form_to_file_no_cover }  
  
  ${action_button_html(url_action('review_all_sections'), icon='edit', label=word("Make changes"))}
  
  % if not defined('email_success') or not email_success:
    ${ action_button_html( url_action('form_delivery_complete'), id_tag="submitToCourt", label="Submit to " + str(courts[0].name), icon=send_icon, size="md", color="primary")}
    
  Or download/email below:
  % else:
    Your email has already been delivered to ${courts[0]}
    
  [:file-download: Download with cover page](${final_form_to_file.url_for()})    
  % endif
progress: 100
attachment code: [PLACEHOLDER: ATTACHMENT VARIABLE]
section: download
```
