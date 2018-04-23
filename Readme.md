# How to use ASPxRichEdit to edit RTF data in ASPxGridView's EditForm


This example is based on the <a href="https://www.devexpress.com/Support/Center/p/E4257">How to use ASPxHtmlEditor to edit RTF data</a> one. It illustrates how to accomplish the same task using a new ASPxRichEdit control instead of the ASPxHtmlEditor one

* Add ASPxRichEdit into the related column's EditItemTemplate;
* Handle the ASPxRichEdit.Init event. 
* When editing an existing row, use the corresponding <a href="https://documentation.devexpress.com/#AspNet/DevExpressWebASPxRichEditASPxRichEdit_Opentopic">ASPxRichEdit.Open</a> method overload;<br>    - Pass the documentId value to identify the document to open (for example, generated based on the editing row key/guid). For per-user editing, construct the DocumentID using the row's key plus user info, for example, System.Web.UI.User.Identity.Name. Then, close the document for editing by this DocumentID for this user only;<br>    - Return a stream or an array of bytes value from the 3-rd parameter created from the underlying column value;
* Handle the ASPxGridView RowInserting/RowUpdating events:<br>    - Retrieve the modified rich text content from ASPxRichEdit via the <a href="https://documentation.devexpress.com/#AspNet/DevExpressWebASPxRichEditASPxRichEdit_SaveCopytopic">ASPxRichEdit.SaveCopy</a> method;<br>    - Save it back to the database in the required format (a string or an array of bytes value).<br><br><strong>Note that data modifications are not allowed in online demos. To allow editing in local/offline mode, download the example and comment out the "throw..." operation in the ASPxGridView.RowUpdating event handler.</strong><br><br><strong>See Also:</strong><br><a href="https://www.devexpress.com/Support/Center/p/E4257">How to use ASPxHtmlEditor to edit RTF data</a>

<br/>

