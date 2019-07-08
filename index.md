---
title: Books read by Nick Loadholtes
---

# Hi! Here's things I've read recently (or am currently re-reading)

The [RSS feed](https://www.goodreads.com/review/list_rss/2953838) where I'm getting this info

And here is my [GoodReads.com page](https://www.goodreads.com/user/show/2953838-nick-loadholtes)


## Most recently read:
<style>
	#bookholder{
		display: flex;
		flex-wrap: wrap;
	}
	.book{
	width: 200px;
	margin: 10px;
	}
</style>
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
	var book_details = "<a href=" + el.find("link").text() + ">" +
		"<img src="+ el.find("book_medium_image_url").text()+"></a>" +
		"<br><em>" + el.find("title").text() + "</em>";
	if(el.find("user_rating").text() !== "0") {
		book_details += "<br><b>My rating:" + el.find("user_rating").text();
	} else {
		book_details += "<br><em><b>Still reading...</b></em>"
	}
	box.append("<div class='book'>" + book_details + "</div>");
		});
	}
		});
	});
</script>
 
