# EvenBetterDeferral
This is a script that builds on Haircut's "Better JAMF Deferral" script found here: 
https://github.com/haircut/better-jamf-policy-deferral 

Even Better Deferral adds support for checking running apps and skipping prompt if App to be updated isn't running. 

It also adds support for modifying "Blocking" apps at runtime (i.e. if Keynote is running, suppress update).

And finally, it provides the option to modify the messaging displayed to users at runtime on a per-policy basis, without having to tweak the script itself. 

Future updates may include options for ~~modifying custom messaging at runtime,~~(done!) and program logic for ignoring blocking apps if app to be updated won't require a prompt. 

# Adding the new options

When adding the script to your JAMF library, add the following to Parameter 7: 

    Blocking Apps with comma and no space (e.g. Keynote,Powerpoint, etc)   

and this to Parameter 8:

    App(s) to be updated with comma and no space (e.g. Google Chrome,Microsoft OneNote)

and this to Parameter 9:

    Custom Messaging
   
# Using the new options

When creating a prompt policy with EvenBetterDeferral if there are any applications you wouldn't want to interrupt with a prompt, place these in Parameter 7, separated by a comma and NO SPACE. This is mostly to avoid splashing a warning on an active presentation or similar. 

Parameter 8 should contain the App(s) being updated, or any app you WOULD WANT a display prompt to appear should it be running (i.e. if you're updating WebEx plugins, you may want to notify the user to quit Outlook as well as WebEx). 

Parameter 9 should contain your custom messaging for the update being applied. Something like: 

    Important changes are required for <Application>. Please select a convenient time to apply updates from the list below. 

Other options in the prompt policy don't change, and neither does the cleanup policy. 
