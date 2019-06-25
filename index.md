Hi! here's things I've read recently (or am currently re-reading)


https://www.goodreads.com/review/list_rss/2953838

<script language="JavaScript">
  var conn = new XMLHttpRequest();
  conn.open("GET", "https://cors-anywhere.herokuapp.com/https://www.goodreads.com/review/list_rss/2953838", false);
  conn.setRequestHeader("Content-Type", "text/xml");
  conn.send(null);
  var xmldoc = conn.responseXML;
  var items = xmldoc.childNodes[0].childNodes[1];
  for (var i = 0; i < items.children.length; i++)
  {
   var book = items.children[i];
   var title = book.getElementsByTagName("title");
   var img = book.getElementsByTagName("book_medium_img_url");
   document.write("<tr><td>");
   document.write(title[0].textContent.toString());
   document.write("</td><td>");
   document.write("<img src="+img[0].textContent.toString()+">");
   document.write("</td></tr>");
  }
</script>
 
