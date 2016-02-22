# What is alxpodder

alxpodder.sh is a bash script that can be used to download podcasts using RSS feeds.

alxpodder.sh is heavily based on the bashpodder script by Linc (http://lincgeek.org/bashpodder).

# How does alxpodder works

Basically, alxpodder.sh goes through the links in RSS feeds and compares them with those kept in a database (a textfile called podcast.log) of already downloaded files.
If the file has not been downloaded yet, it is then downloaded and its url kept in the updated database.

The RSS feed(s) alxpodder.sh parses for new podcasts to download are kept in a single textfile (in this repo, the file is called example.apodder).
The information on that file is organized as follows:

For each podcast (see the example.apodder file, it is quite easy):

1. a line with the podcast name (no spaces in the naming is advised)

2. a line where the url of the RSS feed is declared

To use the script, just call it with the file of the RSS feed(s) as argument, for example:
	alxpodder.sh example.apodder

## The first time

## Cleaning a session that did not end properly

If a session is not ended properly, the urls of the files downloaded during that session won't be kept in the podcast.log database (they will be stored in the temporary file temp_pc.log).
In order to avoid downloading the files again in the next session, one can clean the temp_pc.log file and add the urls to the podcast.log database using clean as the argument when calling alxpodder.sh:
	alxpodder.sh clean

## Adding/deleting an entry to the podcast list

This is as simple as adding a two new lines to the RSS feeds database (in this repo, the example.apodder file).
Uneven lines are the podcast name (no spaces in the naming advised), even lines are the RSS urls.

# A miscellaneaous of possible uses

	alxpodder.sh example.apodder
This will download all the podcasts present in the RSS feed that are not in the podcast.log file

	alxpodder.sh clean
This will clean the previous session when it was not ended properly

	alxpodder.sh example.apodder no-download
This will update the already downloaded podcasts database without downloading any podcast.
This might be useful when adding a new RSS feed or when using alxpodder.sh for the first time.
