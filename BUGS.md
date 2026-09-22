# Bug Hunt — BUGS.md

Document each bug you find and fix here. Use this format for each of the five bugs. Three to four sentences per bug is plenty, this is just a diagnostic record (please no essays here).

## Bug 1

**Symptom:** App not loading certain text on screen

**Root Cause:** The text wasn't placed between text tags.

**Fix:** Put the text between text tags.

## Bug 2

**Symptom:** chores won't delete

**Root Cause:** delete chore handler doesn't replace the array, breaks react rules

**Fix:** replace the existing array with a .filter function to rebuild the array without the id that is being deleted

## Bug 3

**Symptom:** incorrect rows deleting when pressing delete button

**Root Cause:** current key extractor references the array position, not the id

**Fix:** pass in the item id instead

## Bug 4

**Symptom:** textbox won't make new textboxes

**Root Cause:** onchange was used in the button instead of onchangetext

**Fix:** replace onchange with onchangetext

## Bug 5

**Symptom:** textboxes will appear on screen after adding a chore but no new text

**Root Cause:** I had not wrapped the text in bug fix #1

**Fix:** wrapped text with a new text wrapper correctly

## Additional Notes

I don't know what other bug was missing, but just ran this through an AI model after completing to confirm. This is working 100% after manual testing as well.
