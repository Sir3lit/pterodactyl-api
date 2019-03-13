# Errors

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- You didn't pass an auth header or it was missing the bearer.
403 | Forbidden -- Your key is invalid or it doesn't have access to said endpoint.
404 | Not Found -- The specified kitten could not be found.
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The kitten requested has been removed from our servers.
412 | Precondition Failed -- You're missing something.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many much! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.