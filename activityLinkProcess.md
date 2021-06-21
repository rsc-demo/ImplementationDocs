# Alt Solution

## GH Activity Block

1.  The block requires the developer to insert a predetermined activityID and an activityName
2.  When rendered for the student or instructor, a script will:
    1.  Use the `sectionID` and `GHactivityID` to look up the inviteURL
    2.  Generate the invitation link on the page:  
        `<a href= “{inviteURL}” [Other Attributes] >{activityName}</a>`

## Process

1.  Create a Google Sheet (probably the best solution for now)
2.  Three columns (whatever order makes it easiest for CP):
    1.  `sectionID` – ID for the section in Matrix (not the section number)
    2.  `GHactivityID` – A predetermined standard activity ID. Best to use a short (8 chars?) random code (alphanumeric if possible)
    3.  `inviteURL` – The invitation link URL
3.  Developer adds a `GHactivityBlock` and types the `GHactivityID` and the `display name` for the activity.
4.  When a new section is created, CP will:
    1.  Copy the block set of `GHactivityID`s to create new record rows
    2.  Create the activities for the new section in GH
    3.  Enter the `sectionID` and `inviteURL` on the Google Sheet

## To Consider
1.  Upon loading the first invite block, would it be more efficient to load all of the activity links into local storage, WebSQL, or IndexedDB?
    - Probably not good for instructors, because it needs to update depending on the section they came in through RL
2.  Might be good to make a page with all of the GHactivityBlocks so instructors don't need to go in and out of every lesson to accept the invites.
    - Instructors will need to first go into any lesson so that the `sectionID` is passed to CourseArc.
    - Then they can click on the bookmarked page to get to the list of invites. They must use the same browser session for it to work.
