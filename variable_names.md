# Variable names to use when editing fields in Adobe Acrobat or the Documate Field Renamer

Below is a list of variable names to use when renaming fields in your template.

Some key things to remember for all field names:

* **Important**: the capitalization of fields is important. **Please use _all lowercase_ field names** for consistency.
* Use short, but descriptive names for each field. E.g., has_household_over_60 for "Tenant or someone in his/her household is 60 years of age or older."
* Use verb-noun pairs for checkboxes. E.g., is_parent, speaks_spanish, has_assets
* For checkboxes with a yes and no pair, use is_parent_yes and is_parent_no

Nod to https://github.com/knod/docassemble-standards/wiki/Standardized-Definitions-For-Variable-Names, 
with some changes because we are using PDFs and not Word Documents.

## Information about people

* user_name_first
* user_name_middle
* user_name_last
* user_name_suffix
* user_name_full (will combine answers for first, middle, last, suffix)
* user_gender_male (checkbox)
* user_gender_female (checkbox)
* user_gender_other (checkbox)
* user_birthdate

* user2_name_first
* user2_name_middle
* user2_name_last
* user2_name_suffix
* user2_name_full (will combine answers for first, middle, last, suffix)
* user2_gender_male (checkbox)
* user2_gender_female (checkbox)
* user2_gender_other (checkbox)
* user2_birthdate

* other_party_name_first
* other_party_name_middle
* other_party_name_last
* other_party_name_suffix
* other_party_name_full (will combine answers for first, middle, last, suffix)

* witness_name_full

* child1_name_first
* child1_name_middle

## Contact information

* user_address_street
* user_address_city
* user_address_state
* user_address_zip
* user_address_on_one_line (variation with all address parts on one line)
* user_address_city_state_zip (variation with just city, state, and zip on one line)
* user_email
* user_phone

* user2_address_street
* user2_address_city
* user2_address_state
* user2_address_zip
* user2_address_on_one_line (variation with all address parts on one line)
* user2_address_city_state_zip (variation with just city, state, and zip on one line)
* user2_email
* user2_phone


## Court information

* court_name (The full name of the court. E.g., Dorchester Division, Boston Municipal Court)
* court_division (E.g., District Court)
* court_name_short (E.g., Lowell, if full name is Lowell District Court)
* docket_number

Below variables will be filled in to have the full name(s) of the various people who fill that role. 
E.g., you might have user/user2 both in the Plaintiff field. It would display as a list with a comma in between

* plaintiff (we'll have a question that says which of the three people we ask about is the Plaintiff/Defendant)
* defendant 
* petitioner
* respondent

## Signatures

This needs to be a **digital signature field**. This option is hidden in some versions of Acrobat.
This may help: https://answers.acrobatusers.com/Create-a-digital-signature-field-in-Acrobat-Pro-DC-q287451.aspx

* user_signature
* user2_signature
* witness_signature
