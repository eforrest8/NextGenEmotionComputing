# For Future Teams

## Known Issues

### Sidebar overflow

The sidebar containing the list of sessions for the current user (SessionSidebar.jsx/SessionDashboard.jsx) has a few related issues. First, it is not scrollable; so if a user has so many sessions that the list would extend beyond the bottom of the page, new sessions will not be accessible. Note that the panel containing the logout button is overlaid on this sidebar, so even if the list was contstrained to the viewport height, the bottom element would likely not be visible.

### Back button placement

The back button shown in the session sidebar is overlaid on the session list and does not scroll properly. It should probably be moved to the panel with the logout button.

### Emotion detection

Emotion detection is only semi-functional at present. This is due to a variety of factors, but chief among them is the nature of the HP Omnicept camera. The camera only captures the mouth, which results in images which off-the-shelf facial recognition models do not handle well. It may be necessary to pull back from detecting emotion to detecting mouth expression; smile/frown, etc.

## Things to Improve

### Session dahsboard

Currently this page is just a list of charts. It would be nice to unify it into something more cohesive; syncing all the timelines was one idea we threw around.

### Unity data saving

JSON data is buffered entirely into memory and written to disk / uploaded at the end of a session. Ideally all data would be streamed to disk, and streaming uploads would also be nice to have.

### Data processing

We do some data processing on the API server at the time the data is requested (video processing, for example.) It would be better to do this processing at the time of upload and save the results instead so as to reduce server load.
