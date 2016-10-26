# Aizoban1
Android manga app

An online and offline Manga reading application for Android.

This Android application allows users to browse a catalogue of mangas from various sources in a local SQLite database. This catalogue can be searched by name and filtered by genres, status, name, and rank. Similarly, users can fetch latest updates for their chosen source. Clicking a manga, launches the MangaActivity in which they can view more information about a chosen manga and a list of available chapters. From this activity, users can either read a chapter online or add it to queue for a later download. When reading a chapter, the user has various reading controls and image gestures. Finally, the application allows the users to maintain their own libraries of downloaded manga, favourite manga, and recent chapters.



Libraries

Cupboard: https://bitbucket.org/qbusict/cupboard/
This library was used to assist persisting the local SQLite database which stored the Manga and another database for application-specific and user data. Furthermore, the ability to work with content values, cursors, and databases by mapping results to POJOs helped the presenters to populate the views and the download manager to maintain a persistent task queue.

Disk Lru Cache: https://github.com/JakeWharton/DiskLruCache
This library was used to persist a chapter's meta data temporarily for online reading.

Event Bus: https://github.com/greenrobot/EventBus
This library was used to loosely couple communication between controllers and presenters in the application. For example, sending querying events to presenters to re-query and to repopulate their views with new data.

FloatingActionButton: https://github.com/makovkastar/FloatingActionButton
Glide: https://github.com/bumptech/glide
This library was used over Picasso (while they have a similar API) for custom Targets and Transcoders which eased the use of the Palette API.

Jsoup: http://jsoup.org/
OkHttp: http://square.github.io/okhttp/
This library was used to conduct all the application's HTTP requests. It was used in favour of using a more abstract library like Volley (which I used originally), so I can more control over the responses without needing custom requests and threading.

Okio: https://github.com/square/okio
RoundImageView: https://github.com/vinc3m1/RoundedImageView
RxJava: https://github.com/ReactiveX/RxJava
This library was relied upon heavily to create an Observable API to fetch my data. Furthermore, it was used to handle most Activity- or Fragment- bound asynchronous tasks. I really enjoyed creating an Observable API as I had complete control of the execution of the code so that in the Activities and Fragments, data would be fetched asynchronously so the UI thread will not be blocked. Meanwhile, the download manager can transpose the API call to blocking alternatives to maintain a synchronous flow of execution. Finally, the rich API set of RxJava eased composing and refractoring implementations of user cases (i.e. mapping cursors to data, zipping multiple cursors, or handling errors...).
