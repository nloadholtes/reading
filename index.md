Hi! here's things I've read recently (or am currently re-reading)


https://www.goodreads.com/review/list_rss/2953838

<div id="bookholder"></div>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<script language="JavaScript">
$(document).ready(function() {
	//feed to parse
	var box = $("#bookholder");
	var feed = "https://cors-anywhere.herokuapp.com/https://www.goodreads.com/review/list_rss/2953838";
	$.ajax(feed, {
	accepts:{
		xml:"application/rss+xml"
	},
	dataType:"xml",
	success:function(data) {
		//Credit: http://stackoverflow.com/questions/10943544/how-to-parse-an-rss-feed-using-javascript

	$(data).find("item").each(function () { // or "item" or whatever suits your feed
	var el = $(this);
	box.append("<li>" +
		"<a href=" + el.find("link").text() + ">" +
		"<img src="+ el.find("book_medium_image_url").text()+"></a>" +
		"<br>" + el.find("title").text() +
		"</li>");
		});
	}
		});
	});
</script>
 
