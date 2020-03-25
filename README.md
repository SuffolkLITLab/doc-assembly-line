# The Document Assembly Line Project

We are starting an assembly line to rapidly create mobile-friendly online court forms and _pro se_ materials for key areas of urgent legal need amid the COVID-19 crisis. We're operating out of [Suffolk Law's Legal Innovation and Technology Lab](https://suffolklitlab.org/) in cooperation with the Massachusetts [Access to Justice Commission](http://www.massa2j.org/a2j/)'s COVID-19 task force. Though we're focused on MA specific content, we're sharing our work here in the hopes that our efforts can be replicated in other jurisdictions. All novel code we generate will be licensed under an [MIT License](https://github.com/SuffolkLITLab/doc-assembly-line/blob/master/LICENSE), and we're intentionally building on the open source [docassemble](https://docassemble.org/) platform. Here's [what we're doing](https://github.com/SuffolkLITLab/doc-assembly-line#what-we-are-doing), and [how you can help](https://github.com/SuffolkLITLab/doc-assembly-line#how-you-can-help).

Want to volunteer? [Fill out this form](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform). _Note: the situation is quickly evolving, and everything here could change at any moment._

## What We Are Doing

In the near term, we'll be producing [docassemble](https://docassemble.org/) interviews for a subset of existing court forms. We will be focusing on those forms most needed in the crisis. Interviews will be hosted on a server maintained by the Lab for the courts. Court personnel will be given secure direct access to completed forms on the server. Consequently, the public will be able to initiate and file these forms with the court from their phones or a computer without the need to save, print, sign and mail or upload documents.

Overtime, we will expand the number of forms offered and work to provide more context and assistance to users working through the interview. That is, at first, our interviews will just be mobile-friendly versions of existing forms that one doesn't need to mail or deliver in person. This, however, will change over time as more context is added to help guide users through the process.

Our current workflow is as follows (and though we make the workflow sound linear, we'll be running most of these tasks in parallel):

1. **The court and other stakeholders identify and give us copies of existing forms to automate**. We're actively working on convening these stakeholder groups, but please share this page our our [volunteer sign up](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform) with any relevant channels you can think of (e.g., email lists or Slack Teams).
2. We will do some light preprocessing, but mostly we're just throwing forms into a collection and **batch processing them to auto generate docassemble templates**. The expectation is that we're dealing primarily with PDF files. Preprocessing will primarily involve having folks with Adobe Acrobat add and rename variable fields subject to an internal naming convention.
3. We then train subject matter experts (e.g., law students, lawyers, paralegals et al.) on how to **add context to the templates** and have them do just that, reordering things, grouping questions and providing copy for the end user. Note: this is very much about producing MVPs ([minimum viable products](https://blog.crisp.se/2016/01/25/henrikkniberg/making-sense-of-mvp)). For now, that's just online versions of existing forms.
4. We then **review these, iterate as needed, and publish "finished" versions to the server**, allowing the court to access the data directly so as to avoid the need for printing and mailing or using insecure methods like email.

## How You Can Help

We're setting this up as an assembly line so folks can slot into roles that best fit their skills. [Sign up here](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform), and we'll contact you.

- **Are you a legal professional, paraprofessional or student?** Great, if you're comfortable with Adobe Acrobat, we can train you on preprocessing documents, and you can have a go at renaming variables so they make sense. If you've got a gift for explanation, we can train you on docassemble and you can add context for users to help them understand what they're filling out. If you have strong feelings about what forms we need to cover, you can flag them for us and provide copies.
- **Do you have experience with docassemble or python?** You could help train others or help prepare templates for release to the public.
- **Are you an experienced UX designer?** You can provide feedback on interviews as they move through the pipeline.
- **Are you fluent in languages other than English?** We could really use your help to translate material.
- **Do you want to help but didn't answer yes to any of the above?** Then you're the perfect tester. We'd love to have you kick the tires of interviews and tell us what doesn't work/is confusing.

If you're a techie, we're coordinating our docassmble work over on their [Slack team](#assembly-line) under the #assembly-line channel. We're also using [this Trello board](https://trello.com/b/GQIAuPnN/document-assembly-line) to manage the workflow. That being said, if you fill out the [volunteer form](https://docs.google.com/forms/d/e/1FAIpQLSdQcWfVp7CkFJNPuffQF5BlE8qhV26QTjuWZeCVmOaceRPgKw/viewform) we'll be in touch and let you know where you can help.
