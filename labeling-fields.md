# Field Label Names for Docx and PDF files

_Label names to use when editing fields in Adobe Acrobat or the Documate Field Renamer_

<!-- Add links up there to tutorials on how to use those -->

**Table of contents**

1. [The basics](#field-labels-the-basics)
   1. [Information about people](#information-about-people)
   1. [Court information](#court-information)
   1. [Signature date](#signature-date)
   1. [Custom labels](#custom-field-labels)
1. [Advanced lessons](#field-labels-advanced-lessons)
   1. [Custom date fields](#custom-dates)
   1. [More than one of a person or item](#more-than-one)
   1. [Automatically filling fields](#fields-that-the-program-can-fill-in-by-itself)

[![](https://suffolklitlab.org/doc-assembly-line/images/naming_vid.png)](https://youtu.be/qpfZon2M-GU)
Video of overview: [The Basics of Naming Fields](https://youtu.be/qpfZon2M-GU)


# What?

<!-- Section tweaked 04/05 -->
1. Explanations of the use of pre-determined names you should use when labeling fields in a PDF to make automation possible.
1. A refence guide for those pre-determined names.
3. Rules (and some guidelines) for making [custom labels](#custom-field-labels), since most of your labels will be custom labels.

**<ins>You should use the pre-defined labels in here exactly as they appear and only for the specific purposes described below.</ins>**

Don't work on memorizing this material, though. You can take in what's in here and come back to look up specifics later when it you need them.


# Why?

We can create polished multi-lingual plain-language text and questions for all of these pre-set names. Any form that uses these names will get those polished questions automatically.

Also, when a user is completing multiple forms at the same time, if all these names match on all the forms, they will only have to answer each of the questions once. If three forms ask for a first name but use different label names, the user would have to answer that question three times.

Please contact us if you think we missed a commonly used field name that we might add to these automated names.

If you have more questions, please ask us in the Slack channel.

# Field labels: The basics

<!-- These two paragraphs are new as of 04/05 -->

To make label names, we stich together bits of words with meanings. We do that in English too - there are `lamp`s and there's the color `red`. We put those together to describe a `red lamp`. In our labels, that might look a bit more like `lamp_red`. We might call `lamp` a prefix and `red` a suffix, though that kind of language might get complicated if we get into things like `lamp_red_tall`.

These label rules work like that too - you'll combine prefixes and suffixes to build your labels, so look out for that pattern: `prefix_suffix`

**Note:** Every field label in a PDF has to be unique. They cannot be repeated. We'll talk more about that later, but it's good to remember. In a Microsoft Word docx file, there is no rule that the fields need to be unique.

## Figure out who is using your form

Every form is used by someone. Most forms have parties to a case. Some are not filed with a court, so they may only have
a single user. Some are not filed with a court, but still have a user and an opposing or "other" party.

For example: in a Motion to Vacate Default Judgment, the user of the form is always going to be the defendant. In a form that creates a new case,
the user of the form is always going to be the plaintiff or petitioner.

## Information about people

### Label parties to the case with party-specific labels

The person who is using your form and the person who your form's user is opposing should always get one of the
special labels below:

**Note:** We made PDF labels singular because you can't work with lists in many PDF editors. Docx variables representing people are all plural.
Internally, all variables representing people are plural.

PDF label | Docx label | Use case
----------|------------|----------
`user` | `users`, `user[0]`, or `user[n]` (where `n` is any whole number; use sequentially | Will display the full name of the person who is filling out the online form
`other_party` | `other_parties`, `other_parties[0]`, or `other_parties[n]` | The person suing or being sued by the person filling out the form; someone on the "other side" of the case.
`plaintiff` | `plaintiffs`, `plaintiffs[0]`, `plaintiffs[n]` | Plaintiff in the case if we don't know if the plaintiff is the user or other party.
`defendant` | `defendants`, `defendants[0]`, `defendants[n]` | Defendant in the case if we don't know if the defendant is the user or other party.
`petitioner` | `petitioners`, `petitioners[0]`, `petitioners[n]` | Petitioner in the case if we don't know if the petitioner is the user or other party.
`respondent` | `respondents`, `respondents[0]`, `respondents[n]` | Plaintiff in the case if we don't know if the plaintiff is the user or other party.

If the form has room for two people on one side of the case, you can reference `user__1` and `user__1` (on a PDF) or `users[0]` and `users[1]` (in a Docx). It's
important to always use one of these 4 labels for people who are actually part of the case, since we use those internally in many many places in our standard
questions and to communicate information to the court.

Never use names like:

* Tenant
* Landlord
* Parent

etc. that can be converted into party labels, like `Plaintiff` or `Defendant`, if the form is being used by the
tenant or landlord or parent. Every form should have at least one of the 6 party labels above.

It's best to use `user`/`users` and `other_party`/`other_parties` when you know that the form is always used by a plaintiff or defendant. For example,
a form that is always used by a tenant in an eviction case will normally get labeled with `user`/`users` any place that the form mentions 
either `tenant` or `defendant`. In any form that starts a new case, we can always label the PDF with `user` where the `plaintiff` name goes.

### Use one of these exact prefixes for other "people" on the form when at all possible

You may want to use other kinds of labels on the form for miscellaneous people who are
associated with the form, but are not parties to the case. Using one of these labels below
that we have pre-selected tells our tool that these are people, so we can handle things like addresses,
birthdates, etc. correctly.

We can freely add more labels to this list if you need them for your form. Ideally, talk to us about that
before running your form through the wizard.

Never use any of the labels below when the person identified by the label is a party to the case.
For example, if they are the person using the form or the person who is on the opposing side of the case
from the user of the form.

PDF label | Docx label | Use case
----------|------------|----------
`spouse` | `spouses`, `spouses[0]`, `spouses[n]` | A spouse whose information goes on the form but is not a party to the case.
`child` | `children`, `children[0]`, `children[n]` | Any child whose information goes on the form.
`parent` | `parents`, `parents[0]`, `parents[n]` | A parent who is not a party to the case.
`guardian`  | `guardians`, `guardians[0]`, `guardians[n]` | A guardian who is not a party to the case.
`caregiver`| `caregivers` |
`guardian_ad_litem` | `guardians_ad_litem` |
`attorney` | `attorneys` |
`translator` | `translators` | 
`witness` | `witnesses` |
`debt_collector` | `debt_collectors` | 
`creditor` | `creditors` | 

These are are considered the `prefix`es we described before. <!-- Added 04/05 -->

`unknown_role` isn't something our program will account for, but it's a name you can use when you don't know what role name to use. It can remind you (or alert other folks) to get a consult from someone who would know more.

### People suffixes

When these are people, they have similar things we want to record about them. For example, their first name (`name_first`). These will be our `suffixes`. When a field is for a `plaintiff`'s first name, you will combine the two: `plaintiff_name_first`.

These are pre-defined words you can use as field labels for a plaintiff:

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff` | Label for a field that asks for the plaintiff's full name
`plaintiff_name` | The same - label for a field that asks for the plaintiff's full name
`plaintiff_name_first` | Label for a field that asks for the plaintiff's first name
`plaintiff_name_middle` | Label for a field that asks for the plaintiff's middle name
`plaintiff_name_last` | Label for a field that asks for the plaintiff's last name
`plaintiff_name_suffix` | Label for a field that asks for the suffix of the plaintiff's name
`plaintiff_gender` | Label for a text field asking for the plaintiff to write in their gender
`plaintiff_gender_female` | Label for a checkbox for a "female" gender choice
`plaintiff_gender_male` | Label for a checkbox for a "male" gender choice
`plaintiff_birthdate` | Label for a single field for the plaintiff's date of birth
<strong>CONTACT INFORMATION</strong> | 
`plaintiff_address_street` | Label for a field that asks for the plaintiff's house address
`plaintiff_address_street2` | Label for a field that asks for the plaintiff's apartment number
`plaintiff_address_city` | Label for a field that asks for the plaintiff's city address
`plaintiff_address_state` | Label for a field that asks for the plaintiff's state
`plaintiff_address_zip` | Label for a field that asks for the plaintiff's zipcode
`plaintiff_email` |  Label for a field that asks for the plaintiff's email address
`plaintiff_phone` |  Label for a field that asks for the plaintiff's phone number
<strong>SIGNATURE</strong>
`plaintiff_signature` | Label for a single field for the plaintiff's signature

<!-- Should this be in a different document? -->
<!-- **Note:** The signature field needs to be a **digital signature field**. This option is hidden in some versions of Acrobat. This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx -->

<!-- Additional descriptions and examples added 04/05 -->
**What if you need to use a field again, though?** As we said, each field label in a PDF needs to be unique, but some forms ask for a field multiple times. For example, the plaintiff's name might come up more than once. In those cases, you add two underscores (`__`) and a number. This will go on the very end of the label, after all the suffixes. So, `prefix_suffix__2`, `prefix_suffix__3`, and so on:

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff_name_first__2` | Label for the second field that asks for that plaintiff's first name
`plaintiff_name_first__3` | Label for the third field that asks for that plaintiff's first name
`plaintiff__2` | Label for the second field that asks for that plaintiff's full name
`plaintiff__3` | Label for the third field that asks for that plaintiff's full name

And so on.

<!-- What do they see when they try to repeat a name? That would help a lot. -->

**How about the other person/organization types you told me about?**

All these pre-defined suffixes work the same for all of the person/organization types we listed.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`defendant` | Label for a field that asks for the defendant's full name
`spouse_signature` | Label for a field that asks for the spouse's signature
`spouse_signature__2` | Label for a field that asks for the spouse's signature a second time <!-- Example 04/05 -->

And so on.

<!-- [multiple people of a certain type, like multiple plaintiffs](#more-than-one). -->


## Court information

We have some pre-defined words for court information too.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`docket_number` | A label for a field for the form filler to write a docket number. (Not for the court!)
`court_name` | A label to write the full name of the court. E.g., Dorchester Division, Boston Municipal Court.
`court_county` | A label to write the county that the court is in. Note: in many forms, this says 'ss' where the county should go.
<!-- court_division (E.g., District Court) | **not yet implemented** -->
<!-- court_name_short (E.g., Lowell, if full name is Lowell District Court) \| **not yet implemented** -->

You can see `prefix`es and `suffix`es here too. `court` and `name`. They follow similar rules. <!-- Added 04/05; edited 04/13 -->

**Note 1:** `docket_number` here is ONLY for the client(s). It's not for 'court use only' areas of the form.

**Note 2:** Just ignore/delete any drop-down menus for court names in existing court forms. We'll replace that with the name of the court, written out as a new field. You can likely cover up the field by setting a white background.

## Signature date

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`signature_date` | A label for the field to write the date the document was signed.


## But I need to use that label!

What if you have a field that needs one of these special labels?

This is one of the trickier problems. If you find yourself needing one of these "special" labels for another field, you'll need to find another name for it. For example, you can make a custom label that's slightly different and more specific label, like `plaintiff_age_at_time_of_conviction`. Learn more about [making custom labels](#custom-field-labels) further down.

## Custom field labels

Most of your labels will be custom labels, but there are still some rules to follow. Also, we can do some automation with custom labels too if they follow certain patterns. <!-- Tweak custom label expectations 04/05 -->

### _Important Rules_

Some things you really need to do or it will be very hard to write code for the labels:

1. Field names **must start with a letter or underscore** (`_`) - not a number or anything else.
1. Field names can only include **letters, numbers, and underscores**. No spaces or any other character.
1. When you run across a large area that gives room for writing a paragraph, make sure it's one big field. If it's divided into multiple lines, put a message about it in its trello card or on the Slack #assembly-line channel.
<!-- Check this previous one carefully. I'm not sure I understood what was meant. -->
<!-- 1. Keep the length of variable names under 79 characters (unlikely you'll reach this limit, but just to be specific). -->

### _Useful label conventions_

Code is also about communicating with each other. The label names you come up with now are ones people will need to work with in the future. You don't have to do too much, but try not to label things with Adobe's defaults or `field1`, `field2`, and so on.

Here are some suggestions for making helpful labels:

* Please use all lowercase letters for **all labels**. The coders will really appreciate it.
* Separate multiple words in a label with an underscore: `plaintiff_does_love_pie`
* Make the labels descriptive. <!-- examples of good and bad ones -->
* If they can be descriptive _and_ short, that's even better.
* Avoid acronyms and abbreviations, other than very common ones such as `id` for identification.
* When you have several related fields in a row, it could help with automation if you make your own `prefix` and `suffix`es. Make a `prefix` out of the the feature that groups them together, e.g. `asset_checking`, `asset_savings`, etc. It makes alphabetical sorting easier. <!-- Why is that important? -->

** Additional `suffix`es to help with automation:** <!-- Tweaked 04/05 -->

* Use verb/noun pairs for checkboxes. For example, `plaintiff_is_parent`, `defendant_speaks_spanish`, `petitioner_has_assets`, etc.
* For checkboxes with a yes/no pair, add `_yes` and `_no` to the end as an _extra_ suffix. E.g., `defendant_knows_english_yes` and `defendant_knows_english_no` - `prefix_suffix_suffix`


# Thank you!

Thank you for joining us to help make a difference in people's lives!


# Field labels: Advanced lessons

Again, don't try to memorize these. After your first read through, use this more like reference material. <!-- Added 04/05 -->

## Custom dates

```
"Forms keep asking for dates in really weird ways."
- A coder
```

Labels for fields that are asking for a full date should generally end in `_date` (e.g. `incident_date`), but some forms want you to put dates in differently. For example, they want the day, month, or year given separately.

(Remember that `prefix_birtdate` and [`signature_date`](signature_date) are pre-determined labels.)

Let's pretend everyting is about an `incident` just to simplify these examples.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`incident_date` | A label for a field to write the full date of the incident.
`incident_date_day` | A label for a field to write the day of the month of the incident.
`incident_date_month` | A label for a field to write the month of the incident.
`incident_date_day_month` | A label for a field to write both the day and the month of the incident. (Yes, we have run into this)
`incident_date_4_digit_year` | A label for a field to write the 4-digit year of the incident (e.g. 2018).
`incident_date_2_digit_year` | A label for a field to write the 2-digit year of the incident (e.g. 18 as in 02/03/**18**).
<!-- Need to support `incident_2_digit_year` | A label for a field to write the 2-digit year of the incident (e.g. 18 as in 02/03/**18**).-->
<!-- Need to support `incident_4_digit_year` | A label for a field to write the 4-digit year of the incident (e.g. 2018). -->
<!-- `incident_season` | A label for a field to write the season of the incident (e.g. winter). -->


## More than one

What if there are two plaintiffs or three docket numbers? Or multiples of any other item?

This program can hanlde plural values. If we want to talk about more than one "plaintiff", we can say which plaintiff we mean - the first one, the second one, the third one, and so on. We add a number as part of our prefix.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff1_name_first` | Label for a field that asks for the first plaintiff's first name
`plaintiff2_name_first` | Label for a field that asks for the second plaintiff's first name

Each of those "plaintiffs" can have any of the suffixes that were described above. Here's an example of some fields a second plaintiff might be filling in.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff2` | Label for a field that asks for the second plaintiff's full name
`plaintiff2_gender` | Label for a text field asking for the second plaintiff to write in their gender
`plaintiff2_signature` | Label for a single field for the second plaintiff's signature

And so on. The same pattern works with other prefixes, like `child`, `defendant`, and `witness`.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`docket_number3` | Label for a field that asks for the third docket number
`child3_name_first` | Label for a field that asks for the third child's first name
`defendant4_name_first` | Label for a field that asks for the fourth 'party's first name
`witness6_name_first` | Label for a field that asks for the sixth witness's first name

You can combine this rule with `__`. For example, you can combine the prefix of the third `plaintiff` with the post-suffix of the second appearance of a field. That is

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff2__3` | Label for the third appearance of the second plaintiff's full name.
`plaintiff2_signature__3` | Label for the third appearance of the second plaintiff's signature.


## Fields that the program can fill in by itself

If someone puts in their birthdate, why would they have to put in their age somewhere else? The program can figure out how old they are, so it can fill that in by itself. There are some other things it will know how to print as well.

<!--
  TODO: Add to coder documentation:
  Coders - we need to grandfather the old uses in. That is, labelers
  may still use old conventions like `plaintiff_address_on_one_line`
  and `users`.
-->

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiff_age` | Label for a field where the plaintiff's age will be inserted automatically
`plaintiff_address_on_one_line` | Label for a field where the plaintiff's address will be inserted on one line
`plaintiff_address_city_state_zip` | Label for a field where the plaintiff's city, state, and zip will be inserted on one line
`plaintiff_address_block` | Label for a field where the plaintiff's full address will be inserted on 3 lines

There are some lists we can automatically print onto the PDF too.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`plaintiffs` | Label for a field to list all the plaintiffs.
`defendants` | The same for defendants.
`respondents` | The same for respondents

The finished form will show a list of names that makes sense. For example, if there were two (Susan and Talia), you would see "Susan and Talia", and so on.

For the curious: `plaintiff_name__2` and such things work like this under the hood.

# Congratulations! <!-- Edited 04/13 -->

You have made it to the end of all of the current documentation! You've got moxie, that's for sure, and it'll serve you well in life!
