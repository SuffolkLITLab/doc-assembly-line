# Labeling PDF fields

_Label names to use when editing fields in Adobe Acrobat or the Documate Field Renamer_

<!-- Add links up there to tutorials on how to use those -->

## What?

Below we discuss which names to use when relabeling fields in your template, and what to use them for.

**You should only use these label names for these specific purposes.**

There are also suggestions for how to make new custom label names lower down.

## Why?

We can create polished multi-lingual plain-language text and questions for all of these pre-set names. Any form that uses these names will use those polished versions automatically.

Also, when a user is completing multiple forms at the same time, if all these names match on all the forms, they will only have to answer each of the questions once. If three forms ask for a first name but use different label names, the user would have to answer that question three times.

Please contact us if you think we missed a commonly used field name that we should standardize.

## Things we need to think about

<!-- Link to tutorial on editing field names in a PDF at some point -->

There are a few simple factors that we don't usually think about with these forms that are important to point out here.

First, a form can have one "user" (the person filling out their information) or more than one user. That's true for other people that the form collects information about, too. There could be one child or many children.

Second, a form has two kinds of fields.

1. Fields where the user fills in their information for the very first time.
1. Fields where the program can fill in the fields for the user. For example, where the form wants them to put their name down again.

We'll explain how to work with that information in the sections below.

## The labels

### Information about people

We have specific kinds of people that our code will recognize:

Type of person | Meaning
------------|-------------
`user` | A person filling out the form
`child` | A child of a person filling out the form
`other_party` | The opposing party/parties
`witness` | Someone who signs the form to certify that it's an official form

Each of these people have things about them that we want to record. For example, their first name, their gender, and their date of birth.

We use those in combination to create our field names.

#### Labels for fields for the user to fill in

Let's just talk about one user.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user_name_first` | Label for a field that asks for the user's first name
`user_name_middle` | Label for a field that asks for the user's middle name
`user_name_last` | Label for a field that asks for the user's last name
`user_name_suffix` | Label for a field that asks for the suffix of the user's name
`user_gender` | Label for a text field asking for the user to write in their gender
`user_gender_male` | Label for a checkbox for a "male" gender choice
`user_gender_female` | Label for a checkbox for a "female" gender choice
`user_gender_other` | Label for a checkbox for an "other" gender choice
`user_birthdate` | Label for a single field for the user's date of birth
<strong>SIGNATURE</strong>
`user_signature` | Label for a single field for the user's signature
<strong>CONTACT INFORMATION</strong> | 
`user_address_street` | Label for a field that asks for the user's house address
`user_address_street2` | Label for a field that asks for the user's apartment number
`user_address_city` | Label for a field that asks for the user's city address
`user_address_state` | Label for a field that asks for the user's state
`user_address_zip` | Label for a field that asks for the user's zipcode
`user_email` |  Label for a field that asks for the user's email address
`user_phone` |  Label for a field that asks for the user's phone number

**Note** The signature field needs to be a **digital signature field**. This option is hidden in some versions of Acrobat. This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx

If we want to talk about more than one "user", we can say which user we mean - the first one, the second one, the third one, and so on.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user1_name_first` | Label for a field that asks for the first user's first name
`user2_name_first` | Label for a field that asks for the second user's first name

And so on. For example, you might use `user2` for the spouse.

Each of those "users" can have any of the values that were described above. Here's an example of some fields a second user might be filling in.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user2_name_first` | Label for a field that asks for the second user's first name
`user2_name_middle` | Label for a field that asks for the second user's middle name
`user2_name_last` | Label for a field that asks for the second user's last name
`user2_name_suffix` | Label for a field that asks for the suffix of the second user's name
`user2_gender` | Label for a text field asking for the second user to write in their gender
`user2_gender_male` | Label for a checkbox for a "male" gender choice
`user2_gender_female` | Label for a checkbox for a "female" gender choice
`user2_gender_other` | Label for a checkbox for an "other" gender choice
`user2_birthdate` | Label for a single field for the second user's date of birth
`user2_signature` | Label for a single field for the second user's signature

And so on... |

The same pattern works with `child`, `other_party`, and `witness`.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`child3_name_first` | Label for a field that asks for the third child's first name
`other_party4_name_first` | Label for a field that asks for the fourth 'party's first name
`witness6_name_first` | Label for a field that asks for the sixth witness's first name

<!-- TODO: Witness documentation needs to be fixed -->

**Note** If a `user` or other the opposing party is an organization, just use the `user_name_first`, `other_party_name_first`, etc. fields to store their full name.

#### Labels for fields that will be automatically filled in

Sometimes a form asks you for information multiple times. With a digital form we don't always have to make the user do that. There are a few labels for fields that this program can fill in automatically. If a `user` has put in their date of birth, they don't need to then fill in their age in a different section - the program can figure it out.

**Use these labels ONLY for fields the program will fill in. The user will not be asked about these.**

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user_name_full` | Label for a field where the user's full name will be inserted automatically
`user_age` | Label for a field where the user's age will be inserted automatically
`user_address_on_one_line` | Label for a field where the user's address will be inserted on one line
`user_address_city_state_zip` | Label for a field where the user's city, state, and zip will be inserted on one line
`user_address_block` | Label for a field where the user's full address will be inserted on 3 lines

The same goes for each of the other "person types".

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`child_name_full` | Label for a field where the child's full name will be inserted automatically
`child_age` | Label for a field where the child's age will be inserted automatically
`other_party_name_full` | Label for a field where the other party's full name will be inserted automatically
`other_party_age` | Label for a field where the other party's age will be inserted automatically
`witness_name_full` | Label for a field where the witness's full name will be inserted automatically
`witness_age` | Label for a field where the witness's age will be inserted automatically

And the same rules apply for when you have multiple people in these cases.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user2_name_full` | Label for a field where the second user's full name will be inserted automatically
`child2_name_full` | Label for a field where the second child's full name will be inserted automatically
`other_party2_name_full` | Label for a field where the second other party's full name will be inserted automatically
`witness2_name_full` | Label for a field where the second witness's full name will be inserted automatically

**Each PDF field has to have a unique name. What if there are multiple places you need to fill in the same information?**

<!-- What error do they get when they try to do this? That would help a lot. -->

This gets a bit trickier. If you have multiple places where user's full name needs to go, you can't use the label `user_name_full` in all those spots. This is a bit clunky, but it's our best solution for now. You add `__2`, `__3`, and so on for every extra field that needs that label.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user_name_full__2` | Automatically fill in a second field that needs to show the user's full name.
`user_name_full__3` | Automatically fill in a third field that needs to show the user's full name.

ONLY EVER use this method for this reason, never for something else.

**What if you have a field that needs one of these special labels?**

Another one of the trickier problems. If you find yourself needing one of these "special" labels for another field, you'll need to find another way. For example, you can use a slightly different and more specific label:

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`user_name_full_input` | Custom label for a field where the user should fill in their full name
`user_age_input` | Custom label for a field where the user should fill in their age

You might also be able to get more specific, making a custom name using the conventions that are described below for other custom names. For example, if you want to make a label for a field where the user has to put their age at the time of their conviction, you can make your own variable name - `user_age_at_conviction`.

See [Custom labels](#custom-labels) below.

**What if you want to print a list of people, like plantiffs?**

We have four roles we will program in for now: `plaintiff`, `defendant`, `petitioner`, and `respondent`.

First of all, we'll have a question we'll ask to find out what role each person has. Later, you can use the labels below to print a list of them on the form.

Label to use in the PDF | Meaning
------------------------|-----------------------------------
`plaintiff` or `plaintiffs` | A label for a field where you want to list the names of all the plaintiffs
`defendant` or `defendants` | A label for a field where you want to list the names of all the defendants
`petitioner` or `petitioners` | A label for a field where you want to list the names of all the petitioners
`respondent` or `respondents` | A label for a field where you want to list the names of all the respondents

The final form will show a list of names that makes sense. For example, if there were two (Susan and Talia), you would see "Susan and Talia", and so on.

### Court information

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`docket_number` | A label for a field to write a docket number.
`docket_number2` | A label for a field to write another docket number.
`court_name` | A label to write the full name of the court. E.g., Dorchester Division, Boston Municipal Court.
`court_county` | A label to write the county that the court is in. Note: in many forms, this says 'ss' where the county should go.
`court2_name` | A label to write the name of the second court.

<!-- court_division (E.g., District Court) | **not yet implemented** -->
<!-- court_name_short (E.g., Lowell, if full name is Lowell District Court) \| **not yet implemented** -->

As you can see, you can put in labels for multiple courts.

**Note**: just ignore/delete any drop-down menus for court names in existing court forms. We'll replace that with the name of the court, written out as a new field. You can likely cover up the field by setting a white background.

### Signature date

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`signature_date` | A label for the field to write the date the document was signed.


### Dates in general

Labels for fields that are asking for a full date should generally end in `_date` (e.g. `incident_date`), but some forms want you to put dates in differently. For example, they want the day, month, and year given separately.

Let's pretend everyting is about an `incident` just to simplify these examples.

Label to use in the PDF | When to use it
------------------------|-----------------------------------
`incident_date` | A label for a field to write the full date of the incident.
`incident_date_day` | A label for a field to write the day of the month of the incident.
`incident_date_month` | A label for a field to write the month of the incident.
`incident_date_day_month` | A label for a field to write both the day and the month of the incident. (Yes, we have run into this)
`incident_4_digit_year` | A label for a field to write the 4-digit year of the incident (e.g. 2018).
`incident_2_digit_year` | A label for a field to write the 2-digit year of the incident (e.g. 18 as in 02/03/**18**).
`incident_season` | A label for a field to write the season of the incident (e.g. winter).


### Custom labels

#### Important

Some things you really need to do or it will be very hard to write code for the labels. These are those things:

1. Field names _must_ start with a letter or underscore (`_`) - not a number or anything else.
2. Field names can only include **letters, numbers, and underscores**.
3. Keep the length of variable names under 79 characters (unlikely you'll reach this limit, but just to be specific).
4. When you run across a large area that gives room for writing a paragraph, make one big field and give it one label. Don't divide it into individual lines. 
<!-- Check that last one carefully. I'm not sure I understood what was meant. -->

Code is also about communicating with each other. The label names you come up with now are ones people will need to work with in the future. You don't have to do too much, but try not to label things with Adobe's defaults or `field1`, `field2`, and so on.

#### Useful label conventions

Here are some suggestions for making helpful labels:

* Please use all lowercase letters for **all labels**. The coders will really appreciate it.
* Separate multiple words in a label with an underscore: `_`
* Make the labels descriptive. <!-- examples of good and bad ones -->
* If they can be descriptive _and_ short, that's even better.
* When you have several related fields in a row, try to start the labels with the feature that groups them together, e.g., `asset_checking`, `asset_savings`, etc. It makes alphabetical sorting easier. <!-- Why is that important? -->
* Avoid acronyms and abbreviations, other than very common ones such as `id` for identification.
* Use verb/noun pairs for checkboxes and radio buttons. For example, `is_parent`, `speaks_spanish`, `has_assets`: `user_is_parent`, etc.
* For checkboxes with a yes/no pair, add `_yes` and `_no` to the end. E.g., `user_is_parent_yes` and `user_is_parent_no`
* For date variables (other than birthdate), end the question with `_date`. E.g., `a_label_date`

This makes use of work at https://github.com/knod/docassemble-standards/wiki/Standardized-Definitions-For-Variable-Names, with some changes because we are using PDFs and not Word Documents.

## Thank you!

Thank you for joining us to help make a difference in people's lives!
