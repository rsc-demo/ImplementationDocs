This document will have information about the Classroom Structure.

## Important Notes
1. Teachers and admin must be owners on the organization. The classrooms pull their permissions from the organization it is associated with.
2. The organization where student repos will be stored should have strict permissions.
3. Classrooms can be archived. 
   1. It seems that instructors may be able to archive the classes themselves. 
   2. *Need to determine archival process.*

## Classroom Overview
1. The classroom is like a section in RioLearn that contains the student roster and quick access to their repos.
   1. It contains the assignments for the course (and practice activities?).
   2. It contains a list of students.
2. The student repos are stored within a main organization.
   1. All classrooms that point to the organization will have the student repos stored within it.
   2. This could make the org similar to our classweb server with all student information contained within it and org owners can see all student's repos for grade grievance purposes.
   3. Instructors shouldn't need to access the org directly if they use classroom. This should save them from having to hunt for the students' repos if we have multiple sections in the same org.
3. All classrooms have unique links for students to click on.
   1. Students click on a link to be placed into a roster and link up their GitHub account with the roster name.
   2. Students click on the links to accept the assignment, which creates the repo.
4. Classroom rosters can be imported via LTI implementation. 
   1. This is the prefered method.
   2. **I believe this is a manual process for keeping it sync'd. The instructor has to manually sync and pull the information into Classroom.** See [Import Roster from LMS](https://classroom.github.com/help/import-roster-from-lms)
5. When the classroom is set up, the TA and admin need to be added by Course Production.
   1. TAs would be the adjunct faculty/instructional team. We cannot use teams in the org to assign them as a TA/Admin, they have to be added manually. We just have to make sure they are added to the org to be selectable.
   2. A join link for the TA/Admin needs to be sent to them so they have access.
   
## Classroom Process
1. Create an organization for the dept. to store all the main copies of assignments, practice activities. All course repos can exist in the dept. repo.
2. Create a repo(s) of the assignment(s). This is the starter code for the assignment. It can be in a separate org.
   1. One repo for continuous project across lessons, or to submit all lessons in the one repo in different folders. With version history and commits, we could go back to see what a student did for a lesson. This could alleviate those issues of students who may override their work. *I'm leaning more towards this idea currently.*
   2. Multiple repos for one project per lesson. This could get cumbersome for students having to clone each repo for each assignment, though it would reinforce those skills (but it isn't a necessary skill for the course).
   3. Repo(s) for practice activities. I think one repo per course would be sufficient, placing the activities for each lesson in separate folders, each activity has its own steps.md file.
3. Create an organization for student repos.
4. Create a classroom associated with the organization.
5. Create assignments within the classroom using starter code within repos. (**Note** - When GitHub Classroom imports and copies your starter repository, it does not copy your repository’s settings. Instead, use the [Probot Settings](https://classroom.github.com/help/probot-settings) app.)

## Classroom Structure
1. Dept. Org | rsc-comptech
   1. Will contain the main/primary repos from which the classrooms are defined with.
      1. Repos should be defined as templates to help speed up the creation of the repos for students.
   2. Will contain the repos for all courses in the dept. Use naming convention to keep track of the versions.
2. Course Orgs (**IDEA** - What if we made orgs per instructor rather than by course? This way any course they teach would be within an org dedicated to them.)
   1. Have one org per course. e.g., rsc-CIS133DA, rsc-CIS233DA
   2. We have a bit less than 200 students per year in CIS133DA, 80 in CIS233DA, and less than 40 in the other web development courses.
   3. Ways we can define the orgs:
      1. Based upon the course master.
         1. Could lead to a 1000+ repos in over 5 years for CIS133DA - if we only have one repo per student.
         2. If we have a repo per lesson, then that will be 12+/- repos per student; or 2400 repos per year.
      2. Based upon AY (Fall - Summer). e.g., rsc-cis133da-20-21
      3. Based upon term. e.g., rsc-cis133da-4206
      4. Based upon section. e.g., rsc-cis133da-99999
      5. The more orgs we have to create the more we have to go through the process of setting up profiles, permissions, teams, etc.
      6. Orgs can only be created by District/enterprise owners, so time to have them create the org must be accounted in any workflow.
   4. Profile details:
      1. Display name: Rio Salado College {Course}
      2. Email: **Should this point to course support? cis.lead? other?**
      3. Description: This organization is for student repos attached to GitHub Classroom
      4. URL: go to Rio homepage [?]
      5. Logo: use identifier image of Rio logo, unless we use the same one as in the lessons.
   5. Permissions should be limited as follows:
      1. Base member permission: Write
      2. Members cannot create any Repos
      3. Repository invitations: Disabled
      4. Allow members to publish sites: Enabled
      5. Repo visibility: disabled [?]
      7. Repo deletion and transfer: disabled [?]
      8. Issue deletion: disabled
      9. Repo comments: enabled [?]
      10. Repo discussions: disabled [?]
      11. Team creation: disabled
      12. Dependency insights: disabled [?]
      13. Team discussions: disabled - Don't think it will be needed since it is at the org level and not at a course level.
      14. Projects: disabled - don't think it will be needed for web courses
      15. Repo labels. Not sure if needed or will be used. Need to play around with it.
   6. Teams
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
