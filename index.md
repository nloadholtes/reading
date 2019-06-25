Hi! here's things I've read recently (or am currently re-reading)


https://www.goodreads.com/review/list_rss/2953838

<script language="JavaScript">
  // Create a connection to the file.
  var Connect = new XMLHttpRequest();
  // Define which file to open and
  // send the request.
  Connect.open("GET", "https://www.goodreads.com/review/list_rss/2953838", false);
  Connect.setRequestHeader("Content-Type", "text/xml");
  Connect.send(null);
  // Place the response in an XML document.
  var TheDocument = Connect.responseXML;
  // Place the root node in an element.
  var items = TheDocument.childNodes[0][0];
  for (var i = 0; i < items.children.length; i++)
  {
   var book = items.children[i];
   var title = book.getElementsByTagName("title");
   var img = book.getElementsByTagName("book_medium_img_url");
   // Write the data to the page.
   document.write("<tr><td>");
   document.write(title[0].textContent.toString());
   document.write("</td><td>");
   document.write("<img src="+img[0].textContent.toString()+">");
   document.write("</td></tr>");
  }
</script>
 
