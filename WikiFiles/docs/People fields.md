### People or Group

Note 5/8/2014: SetValue is not working in SharePoint 2007. Mostly working in SharePoint 2013 but still seems to have issues.

SetValue sets the field's inputs and then simulates a click on the "Check Names" button. It does NOT do any sort of validation, so using a user's account name is recommended. Also, you may notice a slight delay when setting the value; this is caused by the Check Names button validating the input.

{{
// Get the field
var peopleField = SPUtility.GetSPField('Assigned To');

// Set the field's value
// The value can be either of the following:
// 1. The user's account name
// Don't forget to escape your backslash!
peopleField.SetValue('domain\\myuserid');
// 2. The user's EXACT display name (if it isn't exact then it won't work!)
peopleField.SetValue('Menke, Kit');
// You can use the display name method for groups (if it is enabled for your field)
peopleField.SetValue('Approvers');

// For multi-select fields, separate your values using semicolons (for people or groups):
peopleField.SetValue('Approvers;Designers');

// Gets the value of the people field
var value = peopleField.GetValue();

// Make the people field read only
peopleField.MakeReadOnly();

// Allow the user to edit the field again
peopleField.MakeEditable();

// Hide the field
peopleField.Hide();
}}