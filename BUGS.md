# Bug Hunt — BUGS.md

Document each bug you find and fix here. Use this format for each of the five bugs. Three to four sentences per bug is plenty, this is just a diagnostic record (please no essays here).

## Bug 1

**Symptom:** App not loading certain text on screen

**Root Cause:** The text wasn't placed between text tags.

**Fix:**

<View style={styles.textRow}>
  {isDone && <Text style={styles.checkmark}>{"✓ "}</Text>}
  <Text>{text}</Text>
</View>

## Bug 2

**Symptom:** chores won't delete

**Root Cause:** delete chore handler doesn't replace the array, breaks react rules

**Fix:** replace the existing array with a .filter function to rebuild the array without the id that is being deleted

function deleteChoreHandler(id) {
setChores((currentChores) =>
currentChores.filter((chore) => chore.id != id),
);
}

## Bug 3

**Symptom:** incorrect rows deleting when pressing delete button

**Root Cause:** current key extractor references the array position, not the id

**Fix:** pass in the item id instead

keyExtractor={(item) => item.id}

## Bug 4

**Symptom:** textbox won't make new textboxes

**Root Cause:** onchange was used in the button instead of onchangetext

**Fix:** replace onchange with onchangetext

<TextInput
  style={styles.input}
  placeholder="e.g. Water the plants"
  value={choreText}
  onChangeText={setChoreText}
/>

## Bug 5

**Symptom:** modal doesn't dissapear after adding new chore

**Root Cause:** submit handler doesn't close the modal at all

**Fix:** added functionality to close the modal when submitting a new chore

function submitHandler() {
if (choreText.trim().length === 0) {
return;
}
onAddChore(choreText);
setChoreText("");
onClose();
}
