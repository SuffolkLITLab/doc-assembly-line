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

* the user, and possibly a second/third user, user2, user3, etc., representing co-parties
* children
* the opposing party
* a witness

You can use user2 for the spouse, etc.

If user, user2, or other_party is an organization,
Use the first_name field to store their full name.

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user_name_first | user.name.first
user_name_middle | user.name.middle
user_name_last | user.name.last
user_name_suffix | user.name.suffix
user_name_full (will combine answers for first, middle, last, suffix) | equivalent to str(user)
user_gender (text field) | user.gender
user_gender_male (checkbox) | user.gender == "male"
user_gender_female (checkbox) | user.gender == "female"
user_gender_other (checkbox) | user.gender == "other"
user_birthdate | user.birthdate
user_age | equivalent to user.age_in_years()


Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user2_name_first | users[0].name.first
user2_name_middle | users[0].name.middle
user2_name_last | users[0].name.last
user2_name_suffix | users[0].name.suffix
user2_name_full (will combine answers for first, middle, last, suffix) | equivalent to str(users[0])
user2_gender (text field) | users[0].gender
user2_gender_male (checkbox) | users[0].gender == "male"
user2_gender_female (checkbox) | users[0].gender == "female"
user2_gender_other (checkbox) | users[0].gender == "other"
user2_birthdate | users[0].birthdate
user2_age | equivalent to users[0].age_in_years()


**Note** You can keep adding additional numbers to the user field name to get the same variables--including name, gender, address, etc., up to 10. That has effect of users[1], users[2], etc., but we'll only handle mapping to PDF up to 10.

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
other_party_name_first | other_party.name.first
other_party_name_middle | other_party.name.middle
other_party_name_last | other_party.name.last
other_party_name_suffix | other_party.name.suffix
other_party_name_full (will combine answers for first, middle, last, suffix) | str(other_party)

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
witness_name_full | witness_name_full

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
child1_name_first | child[0].name.first
child1_name_middle | child[0].name.middle
child1_name_last | child[0].name.last
child1_name_suffix | child[0].name.suffix
child1_name_full (variation that combines all 4 part) | str(child[0])
child1_birthdate | child[0].birthdate
child1_gender | child[0].gender
child1_gender_male (checkbox) | child[0].gender == "male"
child1_gender_female (checkbox) | child[0].gender == "female"
child1_gender_other (checkbox) | child[0].gender == "other"

**Note** You can keep adding additional numbers to the child field name--including name, gender, address, etc. E.g., child2_name_full, child3_birthdate, etc., up to 10.


## Contact information

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user_address_street | user.address.address
user_address_street2 | user.address.unit
user_address_city | user.address.city
user_address_state | user.address.state
user_address_zip | user.address.zip
user_address_on_one_line (variation with all address parts on one line) | user.address.on_one_line()
user_address_city_state_zip (variation with just city, state, and zip on one line) | user.address.city + ', ' + user.address.state + ' ' + user.address.zip
user_address_block (variation with full address parts, on 3 lines) | user.address.block()
user_email | user.email
user_phone | user.phone_number


Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user2_address_street | users[0].address.address
user2_address_street2 | users[0].address.unit
user2_address_city | users[0].address.city
user2_address_state | users[0].address.state
user2_address_zip | users[0].address.zip
user2_address_on_one_line (variation with all address parts on one line) | users[0].address.on_one_line()
user2_address_city_state_zip (variation with just city, state, and zip on one line) | users[0].address.city + ', ' + users[0].address.state + ' ' + users[0].address.zip
user_address_block (variation with full address parts, on 3 lines) | users[0].address.block()
user2_email | users[0].email
user2_phone | users[0].phone_number

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
other_party_address_street | user.address.address
other_party_address_street2 | user.address.unit
other_party_address_city | user.address.city
other_party_address_state | user.address.state
other_party_address_zip | user.address.zip
other_party_address_on_one_line (variation with all address parts on one line) | user.address.on_one_line()
other_party_address_city_state_zip (variation with just city, state, and zip on one line) | user.address.city + ', ' + user.address.state + ' ' + user.address.zip
other_party_address_block (variation with full address parts, on 3 lines) | user.address.block()
other_party_email | user.email
other_party_phone | user.phone_number


## Court information

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
E.g., you might have user/user2 both in the Plaintiff field. It would display as a list with a comma or and in between each name.
E.g., Joe Smith and Jane Smith.

We will ask a question to determine which party is the plaintiff/defendant or petitioner/respondent

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
plaintiff | str(plaintiff)
defendant  | str(defendant)
petitioner | str(petitioner)
respondent | str(respondent)

## Signatures

This needs to be a **digital signature field**. This option is hidden in some versions of Acrobat.
This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
user_signature | user.signature
user2_signature | users[0].signature
witness_signature | witness_signature

Label to use in the PDF | internal Docassemble Variable Name
------------------------|-----------------------------------
signature_date | signature_date
