# Reading
Books I'm reading tracked on goodreads.com

## Why
I really like reading, and I when I first found out about Good Reads, I thought it was a great idea!

Plus I think its a good idea to go back and look at what I thought of these books when I read them. I've learned that there's some books I've underrated at the moment, and others I've thought too much of for some reason.

At any rate, inspired by [reading.lol](reading.lol), I decided to take advantage of the RSS feed and hack together a little page to display my own list.

## How
It is pretty simple: HTML, with a bit of javascript (to pull and parse the RSS feed), and a small bit of CSS to attempt to style it all.

Note on the javascript: Since browsers enforce XSS protections this day, I can't pull and parse the RSS feed directly. Instead I'm I'm using a proxy service to pull the feed, apply the appropriate headers, and then send it to the page for parsing.

Hackish, but it works.

I'm not exicited it has a dependency on a 3rd party, but I'm also not in the mood to set up my own server.
