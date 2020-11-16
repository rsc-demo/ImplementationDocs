# Course Development
This file will document ideas and thoughts about how we might develop courses and assignments.

## Course Content
1. The content will be contained within CourseArc.
2. The content will explain the theory portion of what the students need to learn with How To examples.
3. Practice Activities could be stored within GitHub repo(s).

## Projects
1. Directions can reside in a Markdown file (.md). 
2. We can update directions within the main repo that student repos are created from. The changes will only affect new students moving forward.
3. The directions students will be following is contained with the repo so instructors will know what steps they were assigned. 
4. If students attempt to change the directions, instructors will be able to see their changes.
5. We could put a version number within the commit message so instructors can easily see what version the student is assigned.
6. If we want to be able to walk through what a student has done, we can purposefully incorporate steps to have students commit the previous set of steps to the file.
7. We can have a main branch and a development branch. 
   1. Students work in the development branch. 
   2. When we create the assignment in Classroom, we can have a pull request automatically created upon repo creation for feedback from instructors.
   3. Instructors can added comments directly to a line within the student's code so students can see exactly where the issue is and what the issue is.
   4. Instructors could accept the pull request to merge it to the main branch when the student's code is good.
8. We could use GitHub Actions to do some auto-grading, but my initial thought is to not do this so instructors review the code and make comments in the code.
  
## Practice Activities
1. We can have the practice activities within a repo.
   1. The repo could contain all the practice activities within separate folders.
   2. OR we could create a repo per practice activity. **We should take a look at it from a student's perspective to see how easy it would be to set things up in VS code if they end up having a lot of repos.**
2. We can utilize the GitHub Actions to help provide feedback to students automatically to help them learn where their code is wrong and how to fix it.
   1. Current thought is to make this is a Phase II project, but if time allows, sneak it in at the end of Phase I since it is all done in GitHub and shouldn't rely on RL to function.
3. At this time, GitHub Codespaces does not seem to be available for GitHub Classroom. May potentially still need the Try It editor.

**IDEA** - Could (Should) we still utilize the TryCode editor and link it to the student's repo?
1. It could pull in the readme.md file for the steps they need to complete. 
2. It could save to their repo.
3. If we could, then I think we could have one repo for all their practice activities and just point to the correct folder.
4. The online IDE in GitHub for Codespaces in not available at the moment. 
   1. There is a cost associated with it, so we couldn't use it now anyways. And would need Chair/Admin approval.
   2. The only other option would be to use repl.it, but this would force another account to be created by students so hesitant about using this. Also there is a cost associated with it, and the Teams for education feature is in beta so would want to wait anyways. Currently integrated with GitHub Classroom.
5. I wonder if we can push out changes to already created repos if they need to occur.

## Brainstorming Ideas
1. Create an issue to answer questions about topics, explain why they did something.
   1. Or since the pull request is already created, students can add comments with their answers to explain why they did something, explain their process.
