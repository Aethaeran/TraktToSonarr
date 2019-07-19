# TraktToSonarr

This script uses Python 3.7

This is a companion application to add the highly requested ability to synchronize shows from Trakt.tv lists into a Sonarr installation.

# Required python libraries:

* trakt.py
--> pip install trakt.py
* tvdbsimple
--> pip install tvdbsimple

# Configuration:

The first run will create the config file (syncTrakt.conf), you will have to edit it to put in all necessary data.

### Sonarr Section:

* quality = The quality setting passed to Sonarr you want added shows to be added with. 
* rootDirectory = The main directory you are going to save TraktToSonarr in. Defaults to the location it is run from.
* sonarr_apikey = Your sonarr installations API key. Can be found within Sonarr's settings.
* sonarrUrl = The url for your Sonarr server if not locally hosted.
* MonitorSpecials = Set to True or False depending on if you want Season 0 (Typically show specials) to be added as monitored.

## IMPORTANT
To fill out this next section of the configuration file, you will need to create an API in Trakt using this link : https://trakt.tv/oauth/applications/new
* Name
--> whatever you like, but something you'll be able to recognize (ie. 'myTraktToSonarr')
* Redirect URI
--> urn:ietf:wg:oauth:2.0:oob
* After creation, keep the page open! You will need to copy and paste data into their respective places within the configuration file. 

### Trakt Section:

* TraktAppID = This can be found on your app page. It's the last number in the URL (ie: in https://trakt.tv/oauth/applications/xxxxxx would mean your TraktAppID is xxxxxx)
* TraktID = Client ID from app page.
* TraktSecret = Client Secret from app page.
* user = The name of the user who's Trakt list you want to sync to Sonarr.
* TraktWatchList = The name of the list you want to sync to Sonarr. (Set to 'watchlist' to just sync your WatchList)
* ignoreList = This list will be added in Sonarr but not monitored, I use this for shows on Netflix, that way I can see them in the Sonarr calendar, but they won't download.
