### Description (as of version 0.9.1)
The Content Type field is a special field that only appears once multiple content types have been enabled on a list.

### Usage


{code:javscript}
      // On EditForm, a Content Type field is displayed but it won't be available on NewForm
      // If you try to get the field on NewForm, an exception will be thrown and then logged below
      var field = SPUtility.GetSPField('Content Type');

      // Hide the field
      field.Hide();

      // Make the field read only
      //field.MakeReadOnly();

      // Set the value using the display name
      field.SetValue('Item');

      // ... or the content type ID!
      field.SetValue('0x0100DBD234B62463314F8DE3C4AA2635CD51');

      // Setting the value does not force the page postback
      // if you want to trigger the postback, use the Dropdown onchange
      field.Dropdown.onchange();
{code:javscript}

Check out a code example here: https://github.com/kitmenke/sputility/blob/master/examples/contenttype.html.