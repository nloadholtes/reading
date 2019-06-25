Hi! here's things I've read recently (or am currently re-reading)


https://www.goodreads.com/review/list_rss/2953838


{% assign goodreads = site.data.grbooks.GoodreadsResponse %}
{% for rev in goodreads.reviews.review %}
 <div class='book'>
 <a href='{{ rev.book.link }}'>{{ rev.book.title }} </a>
 </div>
{% endfor %}
