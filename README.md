# Movies
Movies - you know, videos, sound &amp; pictures.  Moving pictures with soundtrack.

developers.themoviedb.org

nextjs.org

react-query

tailwind

typescript

tmdb = the movie database . org

https://nextjs.org/docs

https://developers.themoviedb.org/3/account/get-account-details

Getting Started
Authorization

Starting with version 4, we have some new terminology for explaining the two kinds of authentication.

    Application based authentication
    User based authentication

Application based authentication will only let you query public data. For example, things like public lists. User based authentication is user specific, think of this like logging into the TMDb website. You can not only query the same public data as application based authentication but also your own personal data. For example, maybe you have a private list. This makes it easier to control the authenticated request as there is now only a single token in use.

Starting with version 4, we're now using a Bearer token for all user authentication. If you head into your account page, under the API section, you will see a new key listed called API Read Access Token. This key is expected to be sent along as a Authorization header. A simple cURL example looks like the following:

curl --request GET \
  --url 'https://api.themoviedb.org/4/list/1' \
  --header 'Authorization: Bearer <<access_token>>' \
  --header 'Content-Type: application/json;charset=utf-8'

Application calls like a plain GET request to retrieve a public list for example, can still use the api_key query parameter if you wish.

curl --request GET \
  --url 'https://api.themoviedb.org/4/list/1?api_key=<<api_key>>' \
  --header 'Content-Type: application/json;charset=utf-8'

For these app level GET requests, it's your decision which authentication system you want to use. We do however, encourage you to use the new Authorization header for all requests since it's a system you have to use for all application and user requests besides GET regardless. Should you wish to do any user specific actions like rate a movie or edit a list in the future, choosing the Bearer token will be the system you will already be using.
