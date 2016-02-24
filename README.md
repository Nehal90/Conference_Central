# Conference_Central
In this project I learn how to develop a cloud-based API server to support a provided conference organization application that exists on the web as well as a native Android application. The API supports the following functionality found within the app: user authentication, user profiles, conference information and various manners in which to query the data.

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]

## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application using `appcfg.py update .` 


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool


## Project Name
- [conference-central-1222][7]

[7]: https://conference-central-1222.appspot.com/#/  

## Explore Project APIs

- [conference-central-1222.appspot.com/_ah/api/explorer][8]

[8]: https://conference-central-1222.appspot.com/_ah/api/explorer

## Available API

- addSessionToWishlist()				
	Add session to user wishlist (by websafeKey).

- createConference()					
	Create new conference (by name).

- createSession()						
Create new session (by name and websafeConferenceKey).

- deleteSessionFromWishlist()			
	Remove session from user wishlist (by websafeKey).

- getAllSessions()					
	Get all the sessions

- getAnnouncement()					
	Return Announcement from memcache.

- getConference()						
	Return requested conference (by websafeConferenceKey).

- getConferenceSessions()				
	Return conferences created by user (by websafeConferenceKey).

- getConferenceSessionsBySpeaker()	
	Gets all the sessions of a specified speaker (by websafeConferenceKey and speaker).

- getConferenceSessionsByType()		
	Get sessions of a conference by type (by websafeConferenceKey and typeOfSession).

- getConferencesCreated()				
	Return conferences created by user.

- getConferencesToAttend()			
	Get list of conferences that user has registered 
for.

- getFeaturedSpeaker()				
	Get the featured speaker from memcache

- getProfile()						
	Return user profile.

- getSession()						
	Return requested session (by websafeKey).

- getSessionInWishlist()				
	Get wishlist of sessions that user wants to join.

- queryConferences()					
	Query for conferences. Following query fields are available:
	CITY
	TOPIC
	MONTH
	MAX_ATTENDEES

- querySessions()						
	Query for sessions. Following query fields are available:
	SPEAKER
	TYPE_OF_SESSION
	HOUR
	CONFERENCE_NAME

- registerForConference()				
	Register user for selected conference.

- saveProfile()						
	Update & return user profile.

- unregisterFromConference()			
	Unregister user for selected conference.

- updateConference()					
	Update conference w/provided fields & return w/updated info.

- updateSession()						
	Update session w/provided fields & return w/updated info.