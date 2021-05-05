This document will have information about the Classroom Structure.

## Important Notes
1. Teachers and admin must be owners on the organization. The classrooms pull their permissions from the organization it is associated with.
2. The organization where student repos will be stored should have strict permissions.
3. Classrooms can be archived. 
   1. It seems that instructors may be able to archive the classes themselves. 
   2. *Need to determine archival process.*

## Classroom Overview
1. A classroom is a course section that contains the student roster and quick access to their repos.
   1. It contains the assignments for the course (and practice activities).
   2. It contains a list of students.
2. The student repos are stored within a main organization.
   1. Student repos have their username automatically appended to the repo name.
   2. All classrooms that point to the organization will have the student repos stored within it.
   3. All student repos can be seen directly for the org on GitHub. Classroom provides an easy/nice method of viewing the repos directly.
   4. The college retains control of the repos for grade grievance purposes.
   5. Instructors shouldn't need to access the org directly if they use classroom. This should save them from having to hunt for the students' repos if we have multiple sections in the same org.
3. All classrooms have unique links for students to click on.
   1. Students click on a link to be placed into a roster and link up their GitHub account with the roster name.
   2. Students click on the links to accept the assignment, which creates the repo.
4. Classroom rosters can be imported via LTI implementation.
   1. This is the prefered method.
   2. **I believe this is a manual process for keeping it sync'd. The instructor has to manually sync and pull the information into Classroom.** See [Import Roster from LMS](https://classroom.github.com/help/import-roster-from-lms)
5. When the classroom is set up:
   1. Adjuncts/Instructional Teams must be org owners to be added as a Classroom Admin for the section. 
   2. Course product needs to send the join link to adjuncts when the classroom is set up.
   3. We cannot use teams in the org to assign them as a TA/Admin, they have to be added manually. We just have to make sure they are added to the org to be selectable.
   
## Classroom Process
1. Create an organization for the course.
   1. Developer will store all the template repos of assignments, practice activities, and keys.
   2. The org will be used for GH Classroom and stores student repos.
2. Create a repo(s) of the assignment(s). This is the starter code for the assignment. It can be in a separate org. **Note:** A best practice may be to have one repo as a working repo where changes could occur, which is then merged into the template repo to ensure that any edits being worked on do not get copied over to students while being worked on. Also, it would be good to squash commit histories so changes that have occurred over time do not confuse students and to ensure the git does not get too large for students to clone.
   1. One repo for continuous project across lessons, or to submit all lessons in the one repo in different folders. With version history and commits, we could go back to see what a student did for a lesson. This could alleviate those issues of students who may override their work.
   2. Multiple repos for one project per lesson. This could get cumbersome for students having to clone each repo for each assignment, though it would reinforce those skills (but it isn't a necessary skill for the course).
   3. Repo(s) for practice activities. I think one repo per course would be sufficient, placing the activities for each lesson in separate folders, each activity has its own steps.md file.
3. Create a classroom associated with the organization.
4. Create assignments within the classroom using starter code within repos. (**Note** - When GitHub Classroom imports and copies your starter repository, it does not copy your repository’s settings. Instead, use the [Probot Settings](https://classroom.github.com/help/probot-settings) app.)

## Classroom Structure
1. Dept. Org | rsc-comptech
   1. Will contain the main/primary repos from which the classrooms are defined with.
      1. Repos should be defined as templates to help speed up the creation of the repos for students.
   2. Will contain the repos for all courses in the dept. Use naming convention to keep track of the versions.
2. Course Orgs
   1. Have one org per course. e.g., rsc-CIS133DA, rsc-CIS233DA
   2. We have a bit less than 200 students per year in CIS133DA, 80 in CIS233DA, and less than 40 in the other web development courses.
   3. The more orgs we have to create the more we have to go through the process of setting up profiles, permissions, teams, etc.
   4. Orgs can only be created by District/enterprise owners, so time to have them create the org must be accounted in any workflow.
   5. Naming convention will utilize the following with hyphens in between each item:
      1. Rio's abbreviation: RSC
      2. The course number and module: e.g., CIS233DA
      3. The modality: e.g., IN
      4. Version within RioLearn Course Definition: e.g., v8
      5. Example course organization: rsc-cis233DA-in-v8
   6. Org profile details:
      1. Display name: Rio Salado College {Course}
      2. Email: **Should this point to course support? cis.lead? other?**
      3. Description: This organization is for student repos attached to GitHub Classroom for {Course}
      4. URL: https://www.riosalado.edu/degrees-certificates/computer-and-information-technology
      5. Logo: use logo used within the lessons
   7. Permissions should be limited as follows:
      1. Base member permission: No Permissions
      2. Members cannot create any Repos
      3. Repository Forking: Disabled
      4. Repository invitations: Disabled
      5. Allow members to publish sites: Enabled
      6. Repo visibility: disabled
      7. Repo deletion and transfer: disabled
      8. Issue deletion: disabled
      9. Repo comments: enabled
      10. Repo discussions: enabled
      11. Team creation: disabled
      12. Dependency insights: enabled
      13. Team discussions: disabled - Don't think it will be needed since it is at the org level and not at a course level.
      14. Projects: disabled - don't think it will be needed for web courses
      15. Repo labels. Not sure if needed or will be used. Need to play around with it.
   8. Teams
      1. Something to test - creating Teams and assigning them as TA/Admins in Classroom.

## Classroom creation
1. Add a classroom with pertinent information.
   1. Name (suggested format): {Term}-{Course}-{Section}
   2. Organization account (where student repos reside): Course Org
   3. Connect to LMS for roster management: **Need to set up with programming**
2. There may be problems with CP creating the classrooms since it will be under their account. 
   1. **Should we set up accounts for adjuncts so we know the UN/PW and CP can log into their account to set things up for them. I believe Math does this for MyMathLab.**
   2. This idea would cause problems with allowing them to use their personal accounts. And we would not want to use accounts set up with Azure AD since the password would be same as HCM, etc.

## Assignment creation
1. Assignment information must be documented during development so Course Production can implement it correctly.
   1. Assignment title
   2. Custom Repo prefix - maybe add the section number to help easily identify within the course org
   3. No deadline
   4. Individual assignment
   5. Private visibility - need to verify that org owners can still see repos as it says "only visible to student and classroom owners."
   6. No student admin access
2. Identify where the starter code is. ORG/Repo
3. Branches from template repo are copied over. 
   1. If the feedback feature is enabled, this will create 3 branches. 
   2. Maybe we just have students work in the main branch (though this is not a good practice to develop/teach). **See Feedback Feature info below.**
4. The feedback feature creates a pull request to show all commits applied to the main branch. 
   1. If students use a development branch, they would need to merge their development branch with main branch to be able to use the feedback feature.
   2. The feature is essentially pulling the changes from the main branch and merging it with the feedback branch.
   3. Instructors are automatically subscribed to the pull request so they'll get emails any time a student pushes a commit. 
      1. If they are doing a lot of commits while working on their assignment, instructors would get a ton of emails.
      2. This fact makes using the development branch the better option with students work. And then students merge it with the main branch to "submit" their assignment to the instructor.
      3. Instructors would get an email saying it is submitted. Vs. a Perception submission. Grades could be entered into RL.
