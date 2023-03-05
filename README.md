<h1>Movies</h1>
<h4>Movies - you know, videos, sound &amp; pictures.  Moving pictures with soundtrack.</h4>

<ul>
    <li>developers.themoviedb.org</li>
    <li>nextjs.org</li>
    <li>react-query</li>
    <li>tailwind</li>
    <li>typescript</li>
</ul>

<h3>tmdb = the movie database . org</h3>

<h4>https://nextjs.org/docs</h4>

<h4>https://developers.themoviedb.org/3/account/get-account-details</h4>

<h1>Getting Started</h1>

<h2>Authorization</h2>

<p>Starting with version 4, we have some new terminology for explaining the two kinds of authentication.</p>
<ul>
    <li>Application based authentication</li>
    <li>User based authentication</li>

<p>Application based authentication will only let you query public data. For example, things like public lists. User based authentication is user specific, think of this like logging into the TMDb website. You can not only query the same public data as application based authentication but also your own personal data. For example, maybe you have a private list. This makes it easier to control the authenticated request as there is now only a single token in use.</p>

<p>Starting with version 4, we're now using a Bearer token for all user authentication. If you head into your account page, under the API section, you will see a new key listed called API Read Access Token. This key is expected to be sent along as a Authorization header. A simple cURL example looks like the following:</p>

```
curl --request GET \
  --url 'https://api.themoviedb.org/4/list/1' \
  --header 'Authorization: Bearer <<access_token>>' \
  --header 'Content-Type: application/json;charset=utf-8'
```

Application calls like a plain GET request to retrieve a public list for example, can still use the api_key query parameter if you wish.

```
curl --request GET \
  --url 'https://api.themoviedb.org/4/list/1?api_key=<<api_key>>' \
  --header 'Content-Type: application/json;charset=utf-8'
```

<p>For these app level GET requests, it's your decision which authentication system you want to use. We do however, encourage you to use the new Authorization header for all requests since it's a system you have to use for all application and user requests besides GET regardless. Should you wish to do any user specific actions like rate a movie or edit a list in the future, choosing the Bearer token will be the system you will already be using.</p>

<h2>Images</h2>

<p>You'll notice that movie, TV and person objects contain references to different file paths. In order to generate a fully working image URL, you'll need 3 pieces of data: Those pieces are a base_url, a file_size and a file_path.</p>

<p>The first two pieces can be retrieved by calling the API and the third is the file path you're wishing to grab on a particular media object.
    
<p>Here's what a full image URL looks like if the poster_path of /kqjL17yufvn9OVLyXYpvtyrFfak.jpg was returned for a movie:</p>

    <h4>https://image.tmdb.org/t/p/w500/kqjL17yufvn9OVLyXYpvtyrFfak.jpg</h4>
