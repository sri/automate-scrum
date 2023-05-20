# automate-scrum
A way to automate the mechanics of daily scrum

I run a daily scrum standup. The team consists of a handful of software engineers, a few QA engineers, and a manager and product.

## Here are the mechanics of daily scrum
* group the engineers and qa engineers and call on them, in randomized order, to get their status update
* finally, call on the manager and product in a randomized order
* while each team member is talking, display their tickets in a browser window
* add things that need to be discussed in detail to the "After Party", which occurs at the end of standup

## Software stack
* Mac OS X
* Alfred, to invoke scripts from a key binding
  * Alt-N, move to the next team member
  * Alt-P, add current team member to the After Party and move to the next one
* Emacs, to display to the order of each team member
  * also highlights the current speaker
* AppleScript, used to execute Javascript in the context of the current browser window, which is opened to JIRA
* Python/Ruby, executes the initial list
* JIRA, used for project management
* QuickTime, to record each team members name to MP3
* afplay, to speak out their names

## How I use it
1. I hit Command-Space, which opens up Alfred, and type "scrum"; this runs an alfred workflow the executes the Python/Ruby script. This script creates the randomized groupings of the team members and launches Emacs and opens up JIRA sprint board in a browser tab. The Emacs instance is given the server name "scrumemacs" so that it won't interfer with you 
2. The Emacs instance opens up on the left corner (0, 0) of the Desktop. I have a black Desktop background and Emacs also shows up without any window decoration in black, which makes it look as though the text displayed is part of the Desktop.
3. Another Alfred workflow is bound to Alt-N; it highlights the current team member in Emacs, speaks their name (if the associated MP3 file exists) and selects their tickets in the JIRA sprint board.
4. The Alt-P Alfred workflow, does the same things as Alt-N, but add the users names to the After Party section in Emacs
