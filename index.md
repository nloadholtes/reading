---
title: Books read by Nick Loadholtes
---

# Hi! Here's things I've read recently (or am currently re-reading)

The [RSS feed](https://www.goodreads.com/review/list_rss/2953838) where I'm getting this info

And here is my [GoodReads.com page](https://www.goodreads.com/user/show/2953838-nick-loadholtes)

<style>
	#bookholder, #currently-reading{
		display: flex;
		flex-wrap: wrap;
	}
	.book{
	width: 200px;
	margin: 10px;
	}
</style>
## Currently Reading

<div id="currently-reading"></div>

## Previous Read

<div id="bookholder"></div>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<script language="JavaScript">
$(document).ready(function() {
	//feed to parse
	var box = $("#bookholder");
	var current = $("#currently-reading");
	var feed = "https://cors-anywhere.herokuapp.com/https://www.goodreads.com/review/list_rss/2953838";
	$.ajax(feed, {
	accepts:{
		xml:"application/rss+xml"
	},
	dataType:"xml",
	success:function(data) {
		//Credit: http://stackoverflow.com/questions/10943544/how-to-parse-an-rss-feed-using-javascript

	$(data).find("item").each(function () {
	var el = $(this);
	var book_details = "<a href=" + el.find("link").text() + ">" +
		"<img src="+ el.find("book_medium_image_url").text()+"></a>" +
		"<br><em>" + el.find("title").text() + "</em>";
	if(el.find("user_rating").text() !== "0") {
		book_details += "<br><b>My rating:" + el.find("user_rating").text();
	} else {
		book_details += "<br><em><b><span style='background-color:currentColor'><span style='color:white'>Started on:" + el.find("user_date_added").text().substr(7, 10) +"</span></span></b></em>"
	}
	var divdetails = "<div class='book'>" + book_details + "</div>";
	if(el.find("user_shelves").text() === "currently-reading") {
		current.append(divdetails);
	} else {
		box.append(divdetails);
	}
	});
	}
		});
	});
</script>
 
