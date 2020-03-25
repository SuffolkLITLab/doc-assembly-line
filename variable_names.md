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

This makes use of work at https://github.com/knod/docassemble-standards/wiki/Standardized-Definitions-For-Variable-Names, 
with some changes because we are using PDFs and not Word Documents.

## Information about people

If user, user2, or other_party is an organization,
Use the first_name field to store their full name.

* user_name_first
* user_name_middle
* user_name_last
* user_name_suffix
* user_name_full (will combine answers for first, middle, last, suffix)
* user_gender (text field)
* user_gender_male (checkbox)
* user_gender_female (checkbox)
* user_gender_other (checkbox)
* user_birthdate
* user_age


* user2_name_first
* user2_name_middle
* user2_name_last
* user2_name_suffix
* user2_name_full (will combine answers for first, middle, last, suffix)
* user2_gender (text field)
* user2_gender_male (checkbox)
* user2_gender_female (checkbox)
* user2_gender_other (checkbox)
* user2_birthdate
* user2_age


**Note** You can keep adding additional numbers to the user field name to get the same variables--including name, gender, address, etc., up to 10.


* other_party_name_first
* other_party_name_middle
* other_party_name_last
* other_party_name_suffix
* other_party_name_full (will combine answers for first, middle, last, suffix)


* witness_name_full


* child1_name_first
* child1_name_middle
* child1_name_last
* child1_name_suffix
* child1_name_full (variation that combines all 4 part)
* child1_birthdate
* child1_gender
* child1_gender_male (checkbox)
* child1_gender_female (checkbox)
* child1_gender_other (checkbox)


**Note** You can keep adding additional numbers to the child field name--including name, gender, address, etc. E.g., child2_name_full, child3_birthdate, etc., up to 10.


## Contact information

* user_address_street
* user_address_street2
* user_address_city
* user_address_state
* user_address_zip
* user_address_on_one_line (variation with all address parts on one line)
* user_address_city_state_zip (variation with just city, state, and zip on one line)
* user_address_block (variation with full address parts, on 3 lines)
* user_email
* user_phone


* user2_address_street
* user2_address_street2
* user2_address_city
* user2_address_state
* user2_address_zip
* user2_address_on_one_line (variation with all address parts on one line)
* user2_address_city_state_zip (variation with just city, state, and zip on one line)
* user2_address_block (variation with full address parts, on 3 lines)
* user2_email
* user2_phone


* other_party_address_street
* other_party_address_street2
* other_party_address_city
* other_party_address_state
* other_party_address_zip
* other_party_address_on_one_line (variation with all address parts on one line)
* other_party_address_city_state_zip (variation with just city, state, and zip on one line)
* other_party_address_block (variation with full address parts, on 3 lines)
* other_party_email
* other_party_phone


## Court information

* court_name (The full name of the court. E.g., Dorchester Division, Boston Municipal Court)
* court_division (E.g., District Court)
* court_name_short (E.g., Lowell, if full name is Lowell District Court)
* court_county (note: in many forms, this says 'ss' where the county should go)
* docket_number

**Note**: just ignore/delete any drop-down menus for court name in existing court forms. We'll replace with the name of the
court, written out as a new field. You can likely cover up the field by setting a white background.

Below variables will be filled in to have the full name(s) of the various people who fill that role. 
E.g., you might have user/user2 both in the Plaintiff field. It would display as a list with a comma or and in between each name.
E.g., Joe Smith and Jane Smith.

* plaintiff (we'll have a question that says which of the people we ask about is the Plaintiff/Defendant)
* defendant 
* petitioner
* respondent

## Signatures

This needs to be a **digital signature field**. This option is hidden in some versions of Acrobat.
This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx

* user_signature
* user2_signature
* witness_signature
