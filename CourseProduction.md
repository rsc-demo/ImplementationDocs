# Process for Course Production
This readme file contains the steps and process that Course Production will need to use to set up Classrooms within Github and prepare the invitation links for students.

## Overview of Process
1. Log into [GitHub Classroom](https://classroom.github.com) with the Course Production account.
2. Create a new Classroom associated with the course organization. See Create a Classroom
3. Create the necessary assignments within the new classroom. See Create an assignment.
4. Copy the assignment invitation link for the first assignment to send to the adjunct. See Assignment Invitations.
5. Copy the invitation link for the TAs/Adjuncts to join the classroom. See Invite Adjuncts to Classroom.

## Create a Classroom
1. In [GitHub Classroom](https://classroom.github.com), click on the `New Classroom` button.
2. Select the organization associated with the course that will match the version within Course Definition. e.g., RSC-CIS233DA-V8-IN.
    1. The organization for the course should be created during the course development process by the developer/dept./ID.
3. Type the name of the classroom following this standard: 
    1. {Year}-{Course}-{Section}-{Term}
    2. e.g., 2021-CIS233DA-99999-Fall
4. Click the `Create classroom` button.

For additional help information, refer to the [Manage Classrooms](https://docs.github.com/en/education/manage-coursework-with-github-classroom/teach-with-github-classroom/manage-classrooms#creating-a-classroom) help information on GitHub Docs.

## Create an Assignment
Note, during development a list of the needed assignments will be created with pertinent information to help ensure all the necessary course assignments are set up in Classrooms.

1. If necessary, open the classroom for the desired section.
2. Click on the `Create Assignment` button (or `New Assignment` button if some assignments already exist).
3. Go through the wizard to set up the assignment.
    1. Give the assignment a name based upon the following:
        1. Practive Activities - Lsn#-PracticeActivity - e.g., Lsn2-PracticeActivities
        2. Project Assignments - Lsn#-Project - e.g., Lsn2-Project
        3. Final Exam Projects - Lsn#-FinalExamProject - e.g., Lsn12-FinalExamProject
    3. Check the box below the assignment name to assign a prefix to the student repos. Edit the prefix to list the section number.
    4. Do not assign a due date.
    5. For assignment type, select Individual. Should be selected by default.
    6. For Repo visibility, select Private.
    7. Do NOT check the box to grant student's admin rights to their repo.
    8. Click `Continue`.
    9. Select the associated template for the assignment. The repo will be within the organization associated with the classroom. The name of the repo will match the assignment name with the word `-template` at the end.
    10. Click `Contine`.
    11. For Projects and Final Exam Projects, click the box to Enable feedback pull requests.
    12. Click `Create Assignment`.
4. Repeat steps 2-3 for each additional assignment, practice activity, and final exam project required for the course.

For additional help information, refer to the [Create an Individual Assignment](https://docs.github.com/en/education/manage-coursework-with-github-classroom/teach-with-github-classroom/create-an-individual-assignment#creating-an-assignment) help information on GitHub Docs.

## Assignment Invitations
1. If needed, open the classroom for the desired section.
2. Under the `Assignments` tab:
    1. Find the first assignment, the practice activity within the Course Introduction.
    2. Click on the Invite link drop down.
    3. Click on the Copy to clipboard button next to the listed URL.
3. Paste the link into the email that is sent to the adjunct in the appropriate location.

## Invite Adjuncts to Classroom
NOTE: All adjuncts must have the admin role within the organization related to course. This must be done before they can accept the link. This only needs to occur the first time they teach a new version of the course. They will remain admin for any subsequent sections for that course version.

1. If needed, open the classroom for the desired section.
2. Click on the `TAs and Admin` tab.
3. Double check that the adjunct is an admin for the organization by opening the `Invite TAs and admins to your GitHub organization` link. Best practice is to open it in a new tab so you don't navigate away from Classrooms.
    1. You can use the Role drop down to display only those individuals who have the `Owner` role. 
    2. If the adjunct is not listed, add the instructor to the organization. **Need to figure out how to give CP the adjunct's GH username.**
    3. If the adjunct is listed there, move on to step 4.
4. Under the Invite Admins section, copy the link that is provided there.
5. Using the email template to notify adjuncts that Classrooms is set up for them, paste the Invite Admins link within the appropriate location.

### Email Template to Adjuncts
Dear {Adjunct},

Your {Course} {Section} course is utilizing a third-party application, GitHub Classrooms, to help manage the practice activities and project assignments for the course. To be able to access the students' repos, you will need to log into GitHub Classrooms with your account. The following details will help you find the appropriate classroom. 

Before you can view the classroom, you must follow the Admin Invitation Link below to accept and get permissions. **This is required** for you to view your students' repos and provide feedback on their assignments.

    **Course Name**: 
    **Admin Invitation Link**: 
    **First Assignment Invitation Link**: 

Please use the First Assignment Invitation Link to post a course announcement, using the announcement template provided by your department, so students can accept the first assignment in the course. All subsequent assignment invitation links that students require can be found when they navigate to GitHub Classrooms and sign in with their account.
