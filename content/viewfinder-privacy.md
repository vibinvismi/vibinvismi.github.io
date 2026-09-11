---
title: "Viewfinder privacy policy"
build:
  list: never
  render: always
---

*Last updated 11 September 2026*

[Viewfinder](/viewfinder/) is a personal publishing tool I run for my own social media
accounts. It has no users other than me, and it processes no other person's data.

### Google user data it accesses

Viewfinder requests two Google OAuth scopes, and only against my own Google Account:

- `youtube.upload`, to upload video files to my own YouTube channel.
- `youtube.readonly`, to read back those videos' view, like and comment counts, and their
  upload and privacy status.

It reads no other Google data. It does not touch Gmail, Drive, Contacts, Calendar or
location, and it requests no profile information beyond what the authorisation itself
returns.

### How that data is used

Video files, along with their titles, descriptions and tags, are sent to YouTube in order
to publish them. The statistics read back are used only to compare how my own posts
perform. Nothing is used for advertising, for profiling, or to train a machine learning
model.

### How it is stored

Everything is stored locally on hardware I own, on my home network. There is no cloud
database and no server anyone else can reach.

- The OAuth refresh token is held in a single file readable only by the account that runs
  the application.
- Video identifiers and the statistics read from YouTube are held in a local SQLite
  database.

### How it is shared

Google user data obtained through these scopes is not sold, not transferred to any third
party, and not shared with anyone.

For completeness about what else the application talks to: it publishes my own media and
text to other social platforms, and for one of those platforms it first places a media
file in cloud object storage I rent, so that the platform can fetch it. Neither
destination receives any Google account data, and no Google user data leaves my own
hardware other than to Google itself.

Viewfinder's use of information received from Google APIs adheres to the
[Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy),
including the Limited Use requirements.

### Retention and deletion

The refresh token is kept until it is revoked or the application is retired, at which
point the token file is deleted. Statistics are kept for as long as I find them useful and
can be deleted along with the local database at any time.

Access can be withdrawn at any time from
[Google Account permissions](https://myaccount.google.com/permissions), which immediately
invalidates the stored token.

### Contact

Questions about this application go to the support email shown on the Google consent
screen when authorising it.
