# Variable/field names to use when editing fields in Adobe Acrobat or the Documate Field Renamer

Below is a list of names to use when renaming fields in your template, and suggestions for adding new ones.
The advantage of using the same names we picked out below is that we will able to write great, multi-lingual, plain-language
versions of all of the questions for the standard names, and we'll use those on all of the interviews.

The fields we picked out below will also be saved as default on the server, so that someone can re-use them on a different form. Often, 
one issue requires filling in 3-4 forms. This is an important time-saving feature.

Please contact us if you think we missed a commonly used field name that we should standardize.

In some cases, a single variable name below will also contain the power of multiple individual variables. For example, 
`user_address_on_one_line` will be the user's full address for you to place in a convenient location in the PDF, but the 
user will be prompted for it in parts.

Names communicate meaning. In PDF forms, every field needs a unique name. We will make use of those same names you use in the PDF in the 
Docassemble interviews that we create. They'll be referenced by coders, subject matter experts, and people who are reading the PDF form
and aren't experts in coding or in the applicable law. We need to choose names that communicate meaning to all of those different
participants in building this interview.

The most important thing to do when naming fields is to use names that help us communicate. They should be clear, concise, and 
consistent, both within a single form and from form to form.

Some rules for naming fields:

<!--
  What's the deal with is_parent_yes/no? That's not for a variable name,
  that's for a variable value
-->

## Naming conventions

* Please use all lowercase characters for all fields.
* Field names can only include letters, numbers, and underscores, and they _must_ start with a letter or underscore--not a number.
* Keep the field names short, but descriptive. When you must choose between short length and clarity, choose clarity.
* When you have several related variables in a row, try to start the field name with the feature that groups them, for easy alphabetical sorting. E.g., asset_checking, asset_savings, etc.
* Avoid acronyms and abbreviations, other than very common ones such as ID.
* Separate multiple words in a field name with an underscore.
* Use verb-noun pairs for checkboxes. E.g., is_parent, speaks_spanish, has_assets
* For checkboxes with a yes and no pair, add `_no` and `_yes` to the end. E.g., is_parent_yes and is_parent_no
* For date variables other than birthdate, end the question with `_date`. E.g., filedanswer_date
* Keep the length of variable names under 79 characters (unlikely you'll reach this limit, but just to be specific)

This makes use of work at https://github.com/knod/docassemble-standards/wiki/Standardized-Definitions-For-Variable-Names, 
with some changes because we are using PDFs and not Word Documents.

## Information about people

We have 4 main groups of people:

1. the user, and possibly other users (user2, user3, etc.) representing co-parties
1. a child/children
1. the opposing party/parties
1. a witness(es)

<!--
This needs to be user tested to make sure people actually do this.
If they don't, we need to collect what names they do use for those fields.
Added it as an issue in SMEs board.
-->

You can use user2 for the spouse, etc.

## General notes

1. Alternatives: `user` and `user1` prefixes are treated the same way.
1. Pluralities: When signifying a second or third of anything, you
just increase the number in the prefix. For example, `user2` and `user3`.
1. If users or other_parties is an organization,
use the first_name field to store their full name.
1. Full names will be a combination of the other name parts. It's
built into docassemble as `str()`. For example, `str( users[0] )`.
1. The value of the `gender` text field will be, when needed,
sorted into "Other", "Female", and "Male". There will be a message
to the user letting them know that their custom entry will be used
wherever it's possible.
1. All the individuals can have the fields you see in the `users` fields.



<!--
  Todo: Consider rearranging into different categories.

### Prefixes
With example of users

### Human Information


### Contact Info


### Users

  Todo: Add column for field type.
-->



<!-- Is `use_name_ful` something that a user would fill in? -->

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
`user_name_first` | `users[0].name.first`
`user_name_middle` | `users[0].name.middle`
`user_name_last` | `users[0].name.last`
`user_name_suffix` | `users[0].name.suffix`
`user_name_full` | `str(users[0])`
`user_gender` (text field) | `users[0].gender`
`user_birthdate` | `users[0].birthdate`
`user_age` | equivalent to `users[0].age_in_years()`

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user1_name_first | users[0].name.first
... | ...
user2_name_first | users[1].name.first
... | ...

<!--
  Needed?
**Note** You can keep adding additional numbers to the user field name to get the same variables--including name, gender, address, etc., up to 10. That has effect of users[0], users[1], etc., but we'll only handle mapping to PDF up to 10.
-->

### Children

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
child_name_first | child[0].name.first
child_name_middle | child[0].name.middle
child_name_last | child[0].name.last
child_name_suffix | child[0].name.suffix
child_name_full (variation that combines all 4 part) | str(child[0])
child_birthdate | child[0].birthdate
child_gender | child[0].gender
child1... | child[0]...
child2... | child[1]...

### Other parties

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
other_party_name_first | other_parties[0].name.first
other_party_name_middle | other_parties[0].name.middle
other_party_name_last | other_parties[0].name.last
other_party_name_suffix | other_parties[0].name.suffix
other_party_name_full | str(other_parties[0])

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
other_party1_name_first | other_parties[0].name.first
... | ...
other_party2_name_first | other_parties[0].name.first
... | ...

### Witnesses

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
witness_name_first | str(witnesses[0])
... | ...
witness_name1_first | str(witnesses[0])
... | ...
witness_name2_first | str(witnesses[1])
... | ...


### Contact information
_These fields can be used with other entities, like children, other parties, and witnesses._

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user_address_street | users[0].address.address
user_address_street2 | users[0].address.unit
user_address_city | users[0].address.city
user_address_state | users[0].address.state
user_address_zip | users[0].address.zip
user_address_on_one_line (variation with all address parts on one line) | users[0].address.on_one_line()
user_address_city_state_zip (variation with just city, state, and zip on one line) | users[0].address.city + ', ' + users[0].address.state + ' ' + users[0].address.zip
user_address_block (variation with full address parts, on 3 lines) | users[0].address.block()
user_email | users[0].email
user_phone | users[0].phone_number


### Court information

<!-- Should court have court_address_county to be consistent with the other fields? -->

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
court_name (The full name of the court. E.g., Dorchester Division, Boston Municipal Court) | court
court_division (E.g., District Court) | **not yet implemented**
court_name_short (E.g., Lowell, if full name is Lowell District Court) | **not yet implemented**
court_county (note: in many forms, this says 'ss' where the county should go) | court.address.county
docket_number | docket_number

**Note**: just ignore/delete any drop-down menus for court name in existing court forms. We'll replace with the name of the
court, written out as a new field. You can likely cover up the field by setting a white background.

Below variables will be filled in to have the full name(s) of the various people who fill that role. 
E.g. you might have user/user2 both in the Plaintiff field. It would display as a list with a comma or 'and' in between each name.
E.g., Joe Smith and Jane Smith.

We will ask a question to determine which party is the plaintiff/defendant or petitioner/respondent.

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
plaintiff or plaintiffs | str(plaintiffs) (or something similar)
defendant or defendants | str(defendants) (or something similar)
petitioner or petitioners | str(petitioners) (or something similar)
respondent or respondents | str(respondents) (or something similar)

### Signatures

This needs to be a **digital signature field**. This option is hidden in some versions of Acrobat.
This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user_signature | users[0].signature
... | ...
witness_signature | witnesses[0].signature
... | ...

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
signature_date | signature_date
