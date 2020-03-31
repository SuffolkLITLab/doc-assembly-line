# The Document Assembly Line Project

This project is an assembly line to rapidly create mobile-friendly online court forms and _pro se_ materials for key areas of urgent legal need amid the COVID-19 crisis. We're operating out of [Suffolk Law's Legal Innovation and Technology Lab](https://suffolklitlab.org/) in cooperation with the Massachusetts [Access to Justice Commission](http://www.massa2j.org/a2j/)'s COVID-19 task force. Though we're focused on MA specific content, we're sharing our work [here on GitHub](https://github.com/SuffolkLITLab/doc-assembly-line) in the hopes that our efforts can be replicated in other jurisdictions. All novel code we generate will be licensed under an [MIT License](https://github.com/SuffolkLITLab/doc-assembly-line/blob/master/LICENSE), and we're intentionally building on the open source [docassemble](https://docassemble.org/) platform. Here's [what we're doing](https://github.com/SuffolkLITLab/doc-assembly-line#what-we-are-doing), and [how you can help](https://github.com/SuffolkLITLab/doc-assembly-line#how-you-can-help).

_Note: the situation is quickly evolving, and everything here could change at any moment._

## How You Can Help

We're setting this up as an assembly line so folks can slot into roles that best fit their skills. [Sign up here](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform), and we'll contact you.

- **Are you a legal professional, paraprofessional or student?** Great, if you're comfortable with Adobe Acrobat, we can train you on preprocessing documents, and you can have a go at renaming variables so they make sense. If you've got a gift for explanation, we can train you on docassemble and you can add context for users to help them understand what they're filling out. If you have strong feelings about what forms we need to cover, you can flag them for us and provide copies.
- **Do you have experience with docassemble or python?** You could help train others or help prepare templates for release to the public.
- **Are you an experienced UX designer?** You can provide feedback on interviews as they move through the pipeline.
- **Are you fluent in languages other than English?** We could really use your help to translate material.
- **Do you want to help but didn't answer yes to any of the above?** Then you're the perfect tester. We'd love to have you kick the tires of interviews and tell us what doesn't work/is confusing.

## What We Are Doing

In the near term, we'll be producing [docassemble](https://docassemble.org/) interviews for a subset of existing court forms. We will be focusing on those forms most needed in the crisis. Interviews will be hosted on a server maintained by the Lab for the courts. Court personnel will be given secure direct access to completed forms on the server. Consequently, the public will be able to initiate and file these forms with the court from their phones or a computer without the need to save, print, sign and mail or upload documents.

Overtime, we will expand the number of forms offered and work to provide more context and assistance to users working through the interview. That is, at first, our interviews will just be mobile-friendly versions of existing forms that one doesn't need to mail or deliver in person. This, however, will change over time as more context is added to help guide users through the process.

Our current workflow is as follows (and though we make the workflow sound linear, we'll be running most of these tasks in parallel):

1. **The court and other stakeholders identify and give us copies of existing forms to automate**. We're actively working on convening these stakeholder groups and expect to have more forms from the court soon.
2. We do some light preprocessing, but mostly we're just throwing forms into a collection and **generate docassemble templates**. The expectation is that we're dealing primarily with PDF files.
 -- Preprocessing primarily involves having folks create or rename the variables in a PDF file so they conform to our [internal naming conventions](https://github.com/SuffolkLITLab/doc-assembly-line/blob/master/variable_names.md). Here's the [instructions for renaming variables](https://docs.google.com/document/d/1sxjT0ma5XGNdTz2QeTSCGnyjr8t7eYnOg3icbu-0chM/edit?usp=sharing).
 -- This is followed by the creation of docassemble templates based on the original PDF files. These are created by running the PDFs with renamed variables through our assembly line wizard. Here's the [instructions for using the wizard](https://docs.google.com/document/d/1FDBuHoGnlPUqlTgMcukK3rKMkX0BbSjwj-g8G9_utQQ/edit?usp=sharing)
3. We're also training subject matter experts (e.g., law students, lawyers, paralegals et al.) on how to **add context to the templates** and having them do just that, reordering things, grouping questions, and providing copy for the end user. Note: this is very much about producing MVPs ([minimum viable products](https://blog.crisp.se/2016/01/25/henrikkniberg/making-sense-of-mvp)). For now, that's just online versions of existing forms.
4. We then **review, iterate as needed, and publish "finished" versions to the server**, allowing the court to access the data directly so as to avoid the need for printing and mailing or using insecure methods like email.
5. "Finished" versions of content are then **translated** into multiple languages, reviewed, and published to the server.

### Collaboration Tools

There's also an old school mailing list where we push out stuff that some folks might otherwise miss. If you sign the [volunteer form](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform), we'll invite you.

We have two public Slack Channels:

- One for the whole project over on the [A2J Slack team](https://join.slack.com/t/a2jtech/shared_invite/zt-cniv63yv-lnD7MoeggOSghEd5frFDmA) under the #assembly-line channel.
- The other is where we coordinate docassemble work. This is over on the [docassemble Slack team](https://www.google.com/url?q=https://join.slack.com/t/docassemble/shared_invite/enQtMjQ0Njc1NDk0NjU2LTUyOGIxMDcxYzg1NGZhNDY5NDI2ZTVkMDhlOGJlNTgzZTUwYzNhYTJiMTJmMDYzYjQ0YWNmNjFiOTE5NmQzMjc&sa=D&ust=1585103774503000&usg=AFQjCNHiNBf-O86YH4QDKLBzlcYqiKFiuw), also under the #assembly-line channel.

**Work assignments and to do items are maintained on our Trello boards**:

- [Docassembly Line Backend/Dev Tasks](https://trello.com/b/nOQKrRt5/docassembly-line-backend-dev-tasks)
- [Document Assembly Line](https://trello.com/b/GQIAuPnN/document-assembly-line)
- [Feedback Loop with SME](https://trello.com/b/Ysd1wwoK/feedback-loop-with-sme)
- [Translation](https://trello.com/b/x1OIwMKU/translation)

## Meetings

We have regular meetings via Zoom. You can find recordings of these below:

- March 30, 2020 @ 12:30pm Eastern. [All-hands Kickoff Meeting](https://youtu.be/_7MxwiImPQM)
- March 31, 2020 @ 12:30pm Eastern. [Daily stand up/drop-in](https://youtu.be/LHzUXYrIBMI) + [Introduction to Docassmble](https://youtu.be/ePcDms2-Crk)
- April 1, 2020 @ 12:30pm Eastern. Daily stand up/drop-in  (coming soon)
- April 2, 2020 @ 12:30pm Eastern. Daily stand up/drop-in  (coming soon)
- April 3, 2020 @ 12:30pm Eastern. Daily stand up/drop-in  (coming soon)
