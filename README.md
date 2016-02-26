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


## Files Included:

- conference.py: Contains endpoints and conference logics.
- app.yaml: App configuration.
- cron.yaml: Cronjob configuration.
- main.py: Handler for taskqueue handler.
- models.py: Entity and message definitions including helper methods.
- utils.py: Helper function for retrieving ndb.Models by urlsafe Key string.

## Endpoints Included:

- **addSessionToWishlist()**

Path: 'session/{websafeKey}'
Method: POST
Parameters: websafeKey (required)
Returns: confirmation of session added to user wishlist.
Description: Adds the sessions users wishlist.
---

- **createConference()**

Path: 'conference'
Method: POST
Parameters: name (required)
			topics (required)
			description (optional)
			organizerUserId (optional)
			organizerDisplayName (optional)
			city (optional)
			startDate (optional)
			endDate (optional)
			month (optional)
			maxAttendess (optional)
			seatsAvailable (optional)
Returns: a confirmation that the new session is created.
Description: Create a new session.
---

- **createSession()**						

Path: 'session'
Method: POST
Parameters: name (required)
			websafeConferenceKey (required)
			duration (optional)
			organizerUserId (optional)
			organizerDisplayName (optional)
			highlights (optional)
			startDate (optional)
			startTime (optional)
			hour (optional)
			speaker (optional)
			typeOfSession (optional)
Returns: a confirmation that the new conference is created.
Description: Create a new conference.
---

- **deleteSessionFromWishlist()**	

Path: 'session/{websafeKey}'
Method: POST
Parameters: websafeKey (required)
Returns: confirmation of session deleted from user wishlist.
Description: Remove session from user wishlist.
---

- **getAllSessions()**	

Path: 'session/all'
Method: GET
Parameters: NONE
Returns: a list of all sessions from all conference.
Description: Get all the sessions.
---

- **getAnnouncement()**		

Path: 'conference/announcement/get'
Method: GET
Parameters: NONE
Returns: annoucement.
Description: Return Announcement from memcache.
---

- **getConference()**

Path: 'conference/{websafeConferenceKey}'
Method: GET
Parameters: websafeConferenceKey (required)
Returns: conference.
Description: Return requested conference.
---

- **getConferenceSessions()**		

Path: 'conferece/{websafeConferenceKey}/sessions'
Method: GET
Parameters: websafeConferenceKey (required)
Returns: a list of sessions within a conference.
Description: Return all sessions within a conference.
---

- **getConferenceSessionsBySpeaker()**	

Path: 'conference/sessions/bySpeaker'
Method: GET
Parameters: websafeConferenceKey (required)
			speaker (required)
Returns: a list of sessions within a conference given by specified speaker.
Description: Gets all the sessions of a specified speaker.
---

- **getConferenceSessionsByType()**		

Path: 'conference/sessions/byType'
Method: GET
Parameters: websafeConferenceKey (required)
			typeOfSession (required)
Returns: a list of certain type of sessions within a conference.
Description: Get sessions of a conference by type.
---

- **getConferencesCreated()**				

Path: 'getConferencesCreated'
Method: GET
Parameters: None
Returns: a list of conferences.
Description: Return conferences created by logged in user.
---

- **getConferencesToAttend()**			

Path: 'conference/created_by_user'
Method: GET
Parameters: None
Returns: a list of conferences logged in user registered for.
Description: Get list of conferences that user has registered for to attend.
---

- **getFeaturedSpeaker()**				

Path: 'conference/featured_speaker'
Method: GET
Parameters: None
Returns: featured speaker announcement.
Description: Get the featured speaker from memcache
---

- **getProfile()**			

Path: 'profile'
Method: GET
Parameters: None
Returns: user profile
Description: Get user profile.
---

- **getSession()**						

Path: 'session/{websafeKey}'
Method: GET
Parameters: websafeKey (required)
Returns: session.
Description: Get requested session.
---

- **getSessionsCreated()**				

Path: 'getSessionsCreated'
Method: GET
Parameters: None
Returns: a list of sessions.
Description: Get list of sessions created by current user.
---

- **getSessionInWishlist()**		

Path: 'sessions/wishlist'
Method: GET
Parameters: None
Returns: a list of sessions.
Description: Get wishlist of sessions that user wants to join.
---

- **queryConferences()**

Path: 'queryConferences'
Method: POST
Parameters: filters (required)
			field (required)
			operator (required)
			value (required)
Returns: a list of conference satisfying the query condition.
Description: Query for conferences by following fields.
				CITY
				TOPIC
				MONTH
				MAX_ATTENDEES
---

- **querySessions()**						

Path: 'querySessions'
Method: POST
Parameters: filters (required)
			field (required)
			operator (required)
			value (required)
Returns: a list of conference satisfying the query condition.
Description: Query for sessions by following fields.
				SPEAKER
				TYPE_OF_SESSION
				HOUR
				CONFERENCE_NAME
---

- **registerForConference()**

Path: 'conference/{websafeConferenceKey}'
Method: POST
Parameters: websafeConferenceKey (required)
Returns: confirmation if user is registered for the conference.
Description: Register user for selected conference.
---

- **saveProfile()**			

Path: 'profile'
Method: POST
Parameters: None
Returns: saved user profile
Description: Update & return user profile.
---

- **unregisterFromConference()**

Path: 'conference/{websafeConferenceKey}'
Method: POST
Parameters: websafeConferenceKey (required)
Returns: confirmation if user is unregistered for the conference.
Description: Unregister user for selected conference.
---

- **updateConference()**	

Path: 'conference/{websafeConferenceKey}'
Method: POST
Parameters: websafeKey (required)
Returns: updated conference.
Description: Update conference w/provided fields & return w/updated info.
---

- **updateSession()**

Path: 'session/{websafeKey}'
Method: POST
Parameters: websafeKey (required)
Returns: updated session.
Description: Update session w/provided fields & return w/updated info.


## Design Choice

Each session is created with session name and websafeConferenceKey which makes it easier to create a session without going thru a conference but still keeping the session as a child of a conference. 

I have chosen to make speaker string and didn't make speaker or any other values mandatory for the session to be created since I wasn't speicified in the project description. 

## Additional queries 

I have made four different fields available for session queries which allows more than 2 combinations queries, to be exact I have added 16 different query combinations in the index.yaaml file. The four fields available for session queries are SPEAKER, TYPE_OF_SESSION, HOUR, and CONFERENCE_NAME.

I took care of the inequlity problems related to these quaries using the same filter_format method that was taught in the course. Out of the four query fields, only HOUR is an INT field, which has been taken care of in the code.


