<% # Define variables
  cohort = Cohortable::Cohort.find_by_id(params["id"] || 60)
  start_date = cohort.start_date
  prework_deadline_shortdate = cohort["prework_deadline_shortdate"]
  two_months_out = (start_date <<(2)).strftime("%B")
  one_month_out =  (start_date <<(1)).strftime("%B")
  # date_format[start_date]
  date_format = lambda { |date| date.strftime("%B #{date.day.ordinalize}") }
%>

![CodePath|400](https://camo.githubusercontent.com/746536e3cf96c58fba4ad967861e1b09ec7b269e/687474703a2f2f692e696d6775722e636f6d2f68306d66796f6f2e706e67)

# Thanks for Applying!

Thanks for applying to be a part of our <%= start_date.strftime("%B") %> Android bootcamp! We receive several hundred free applications and as a result we have a multi-step process to select the final participants. Next steps are to:

1. Confirm you are eligible to participate by reviewing course requirements.
2. Setup the android development environment on your computer.
3. Build the required prework project from scratch step-by-step and submit to us on Github ASAP.

**Didn't apply yet?** If you didn't formally apply for the [Android CodePath Bootcamp](http://codepath.com/androidbootcamp), then please apply through the application in the prior link before continuing.

## Timeline

We are often asked about the timeline for the bootcamp application process. Here's an outline:

  * Submit the prework by <%= prework_deadline_shortdate %>. Quick submissions improve your chances as well as completing bonus features.
  * In early <%= one_month_out %>, we will begin phone conversations with those that complete pre-work. I'll ask you a few questions about Java as well as your goals for taking the class.
  * In mid-<%= one_month_out %>, we will begin offering invitations to those accepted to participate.
  * Classes will start sessions on **<%= date_format[start_date] %>** (SF)

## Requirements

This is a program designed and tailored for **experienced software engineers** interested in a highly accelerated plunge into native Android app development. Please note that this course is not appropriate for individuals with no prior professional software experience or for junior developers with less than 2 years of software experience. The success of this course largely depends on surrounding participants with peers that are all within a similar range of experience.

Before starting the pre-work below you should review the following requirements in order to confirm eligibility for this bootcamp:

 1. 1+ years of professional software development experience
 2. Bachelor's degree in CS/Engineering (if not then 2+ years of professional software experience)
 3. Can dedicate 10-20+ hours per week to this course
 4. Physically present in the Bay Area for each on-site session during the 8 week period
 5. Experience developing software with object-oriented programming languages
 6. Existing knowledge of Java or ability to ramp up on the language quickly

In addition, an essential element of the efficacy of this bootcamp is the agreement of each participant to the following structure and expectations:

 * **Required attendance** to all lab and lecture sessions (although we allow for one excused absence). If you miss an unexcused absence, we will ask you to withdraw from the bootcamp.
 * **Required on-time project submission** of the weekly projects. If you submit a late or incomplete project, we will ask you to withdraw from the bootcamp.
 * Interested in collaborating on a group project with a team during the course
 * Can bring a laptop with Mac OS X, Linux or Windows to each session with the required development environment setup

You can also review the [complete list of evaluation criteria](http://courses.codepath.com/snippets/intro_to_android/selection_criteria). Please **review these requirements above** before continuing.

**Do I have enough experience?** For this bootcamp, we are looking for experienced engineers that have been doing **professional software development for at least 1 year**. If you do not have a formal engineering degree, then at least 3 years of sustained development experience. Exceptions to this are rare as we have more suitable learning channels for those without this experience.

**Not eligible?** If you are **not eligible based on the above**, please check our [Android getting started](http://guides.codepath.com/android/Beginning-Android-Resources#beginning-android-resources) guides and/or our [SF Android meetup](http://www.meetup.com/Learning-Android-Development/) for events and learning resources. If you have any questions on your eligibility, feel free to reach out to us at <admissions@codepath.com>.

## Prework

We can only accept a maximum of 25 people in each bootcamp cohort so the next step is to build out and [submit an initial Todo project](http://courses.codepath.com/snippets/intro_to_android/prework) **before <%= prework_deadline_shortdate %>** that will introduce you to several of the basics of Android development:

* First you need to setup Android Studio using [slides](https://docs.google.com/a/thecodepath.com/presentation/d/1iD0sMc-qIG80yZ1AQfDU5nxSAl3Xe4nx-2W_g9yzMSM/edit#slide=id.p) or the [video walkthrough](https://vimeo.com/113893631)
* We recommend you to watch the [First App video tutorial](https://vimeo.com/113893630) which introduces the Android environment and walks you slowly through building a simple application.
* Now you need to develop an [Android todo list application](http://courses.codepath.com/snippets/intro_to_android/prework) as described in that pre-work snippet.
* Once you have completed the ToDo application **including support for editing an item**, please push the project to Github and **submit your pre-work by <%= prework_deadline_shortdate %>** through the [application status dashboard](https://apply.codepath.com/dashboard/). You can also [email us](mailto:admissions@codepath.com) if you run into any problems, we are happy to help.

We will be confirm eligibility and send next steps once you have submitted the project. Please send us the project as soon as possible. If you have any other questions at all, please feel free to email us at <admissions@codepath.com>.

## FAQ

> Is this bootcamp worth participating in?

We think so. Over a thousand engineers and counting have completed a form of this program. We've been fortunate enough to have engineers participate from companies including Google, Apple, Dropbox, Facebook and over 50 others. We've seen many of the engineers successfully transition to mobile development roles full-time or start mobile companies.

> Is this bootcamp really completely free with no strings attached?

Yes. As long as you are eligible and can agree to the expectations outlined above, the bootcamp is completely free of charge for engineers.

> How many hours does this bootcamp really require per week?

Depends. At least 8 hours every week but the bootcamp is project-based with many optional and bonus challenges. We've seen engineers pour in 20+ hours with incredible results.

> As a company, can I pay to train my existing engineers?

Yes. We provide training for companies such as Facebook, Dropbox, Yahoo, Youtube, etc. We also let select startups reserve seats in our public training. For more information, check out our [company services](http://codepath.com/services).

> Where can I read more about this bootcamp?

Check out the [Android CodePath Bootcamp](http://codepath.com/androidbootcamp) page for details.

> Where can I see the breakdown of the content covered week-by-week?

See this [week-by-week curriculum outline](http://courses.codepath.com/snippets/intro_to_android/about_bootcamp#heading-curriculum-outline).

> Can you bring this free bootcamp to [my city here]?

Yes...eventually. Right now we are only in the bay area. We want to bring our bootcamp to cities where we can find company sponsors. If you might be able to help sponsor us, reach out at <contact@thecodepath.com>.

> What do I do if I want to take this course but I am not eligible?

Please check our [Android getting started](http://guides.codepath.com/android/Beginning-Android-Resources#beginning-android-resources) guides and/or our [SF Android meetup](http://www.meetup.com/Learning-Android-Development/) for events and learning resources. If you have any questions on your eligibility, feel free to reach out to us at <admissions@codepath.com>.
