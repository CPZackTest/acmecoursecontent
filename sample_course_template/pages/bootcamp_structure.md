<% unit_count = current_cohort.unit_count || @course.try(:unit_count) %>

## Bootcamp Structure

This evening bootcamp is a <%= unit_count %>-week exploration of the Android development environment, the Android framework and an opportunity to get hands-on practice building Android apps. The overall structure and components of this course are as follows:

- **Weekly Meeting** (120 mins) - We will meet once every week for 2 hours and discuss key Android concepts, do live coding walkthroughs, and introduce fundamental aspects of Android app development. We will also discuss projects and assignments for that week. 
- **Weekly Lab** (120 mins) - We will hold a weekly lab session in-person where we will help answer any questions and address any problems or questions that arise as you all collaborate and build the weekly projects.
- **Weekly Apps** - For the first <%= unit_count / 2 %> weeks of the course, we will be building a new Android app that helps us reinforce and apply the concepts we introduce within this course. Expect the weekly mini-apps to take anywhere from 5-10 hours to complete each week outside of class. These projects will range from a Todo App to an authenticated Twitter Client. Review the @[[weekly projects overview|slides/Weekly Projects Overview.pdf]] for more details. Check out our guide on [[submitting your assignments|Submitting Assignments]] as well.
<% if @cohort.unit_count > 3 %>
- **Course Group Project** - The second half of the course will be focused on a collaborative course-wide project. The class will be broken up into groups of 3 students each, and every group will select a larger project to scope, design and build over the last <%= unit_count / 2 %> weeks. We will provide a list of recommended projects but also will work with each team to help them select their own project ideas if desired. At the end of the course, we will have a _demo day_ showcasing all of these projects. Read more about the [[course-wide group project|Group Project]].
<% end %>

## Bootcamp Resources

During this course, students should be aware of the following pages and resources:

- [Cliffnotes](http://guides.codepath.com/android/Android-Bootcamp-Cliffnotes) - This includes a series of references to reinforce key concepts and topics
- [Troubleshooting](http://guides.codepath.com/android/Troubleshooting-Common-Issues) - Be sure to check out the this guide if you have any problems.
- [[Curriculum Links]] - Detailed listing of various resources available for you while learning Android
- [[Submitting Assignments]] - Guide for how to submit each of the required projects via Github and raising an issue.
<% if @cohort.unit_count > 3 %>
- [[Group Project]] - Description of the stages of the group project including the final presentation.
- [[Wireframing Tools]] - Description of popular wireframing tools to use for your group project.
<% end %>

Reviewing each of these sections ensures that you will get the most out of this course.

## Bootcamp Tips

A few important items to keep in mind during this course:

- The instructors are absolutely **here to help** through **multiple channels**. Our first priority is making sure we help everyone stay engaged and keep up with the projects and concepts. This is a fast-paced <%= unit_count %>-week course but we will be providing assistance online through [discussion Q&A system](https://discussions.codepath.com), videos and with weekly lab sessions.
- Each formal weekly meeting will be **recorded** and **available for viewing** online. This makes it easy for you to review concepts and catch up if you miss one. That said, we still require in-person **attendance to the meetings**. We find that students that do not participate in and attend the meetings usually end up falling behind in the course. 
- Assessment is building **working apps**. Since every student will **build 5 apps** (and contribute to a larger project) along with many other exercises, we do not have additional assessment built in at the current time. No quizzes or tests, no multiple-choice. Your success in this course depends on the **effort** you can **put into the projects**.
- In order to get the **most out of this course**, expect a time investment of about **10-15 hours each week**. 90 mins during our formal topic introductions, 90 mins for our weekly lab, 8+ hours for projects and 3+ hours for review and reading. We encourage you to spend as much time as is feasible **reviewing concepts** and more importantly **building or improving** the apps we create during the <%= unit_count %> weeks.
- Most importantly, remember that this is **all about learning mobile development** and being able to **create useful apps**. We are here to make the process of learning much easier and streamlined, and we hope you will find the course valuable and fun.
