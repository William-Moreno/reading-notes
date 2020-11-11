# Local Storage

---

## Local Storage for Web Applications

Persistent local storage is one of the areas where native client applications have held an advantage over web applications. Historically, web applications have had none of the luxuries that native applications have had for storage.

**Cookies** were invented early in the web's history. And, while they can be useful for small amounts of data and persistent local storage, they have three potentially deal-breaking downsides:

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet _(unless our entire web application is served over SSL)_
- Cookies are limited to about 4 KB of data - enough to slow down our application, but not enough to be terribly useful

**What we really want is:**

- a lot of storage space
- on the client
- that persists beyond a page refresh
- and isn't transmitted to the server

All attempts to achieve this before HTML5 were, ultimately, unsatisfactory.

### Brief History of Local Storage Hacks

- Microsoft invented a great many things and introduced them in _Internet Explorer_. One of them was `userData`.
  - `userData` allows web pages to store up to 64 KB of data per domain. Trusted sites could store up to 640 KB. But there was no allowance for increasing the amount of storage available.
    In 2002, Adobe introduced a feature in Flash 6 properly known as **Local Shared Objects**, but commonly called "Flash cookies". It allows Flash objects to store up to 100 KB of data per domain.
  - By 2006, with the advent of "ExternalInterface" in Flash 8, `dojox.storage` came into being and gave each domain 100 KB of storage "for free", and beyond that prompted the user for each order of magnitude increase in data storage (1 MB, 10 MB, etc.)
- In 2007, Google launched "Gears", an open source browser plugin.
  - Gears provides an API to an embedded SQL database based on SQLite. Once authorized by the user, Gears can store unlimited amounts of data per domain in SQL database tables.
- By 2009, `dojox.storage` could auto-detect Adobe Flash, Gears, Adobe AIR and an early prototype of HTML5 storage.

The emergent pattern here is that all of them are either specific to a single browser, reliant on a third-party plugin. They all expose radically different interfaces, have different storage limitations, and present different user experiences. This is the problem that HTML set out to solve: to provide a standardized API, implementeed natively and consistently in multiple browsers, without having to rely on third-party plugins.

### HTML5 Storage

What is sometimes called "HTML5 Storage" was at one time part of the HTML5 specification proper. Certain browser vendors also refer to it as "Local Storage" or "DOM Storage".

Simply put, HTML5 Storage is a way for web pages to store named key/value pairs locally, within the client web browser. _Like_ cookies, this data persists even after we navigate away from the web site, close our browser tab, exit our browser, or what have you. _Unlike_ cookies, this data is never transmitted to the remote web server. It is implemented natively in web browsers, so it is available even when third-party browser plugins are not. The latest version of pretty much every browser supports HTML5 Storage.

From our JavaScript code, we can access HTML5 Storage through the `localStorage` object on the global `window` object.

### Using HTML5 Storage

HTML5 Storage is based on named key/value pairs. We store data based on a named key, then we can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript. However, the data is actually stored as a string.

Calling `setItem()` with a named key that already exists will silently overwrite the previous value. Calling `getItem()` with a non-existent kew will return `null` rather than throw an exception.

Like other JavaScript objects, we can treat the `localStorage` object as an associative array, which allows the use of square brackets instead of the `getItem()` and `setItem()` methods.

There are also methods for removing the value for a given named key, and clearing the entire storage area _(deleting all the keys and values at once)_.

_Calling `removeItem()` with a non-existent key will do nothing._

Finally, there is a property to get the total number of values in the storage area, and iterate through all of the keys by index (to get the name of each key).

If we call `key()` with an index that is not between 0 - (length-1), the function will return `null`.

### Tracking Changes to the HTML5 Storage Area

We can trap the `storage` event if we want to keep track of when the storage area changes. The `storage` event is fired on the `window` object whenever `setItem()`, or `removeItem()`, or `clear()` is called _and actually changes something_. The `storage` event is supported everywhere the `localStorage` object is supported.

HTML5 Storage provides 5 MB of storage space for each origin.

### HTML5 Storage in Action

To see the storage in action, imagine a game created in a web app without use of local storage. There is the problem that if we close the browser window mid-game, we'll lose our progress. But, using HTML5 Storage, we can save the progress locally, within the browser itself. If we close the browser page during the game and then re-open it, the page should remember our exact position within the game, including the number of moves made, the position of each of the pieces on the board, and even whether a particular piece is selected.

How?

Every time a change occurs within the game, we call this function:

```JavaScript
function saveGameState() {
    if (!supportsLocalStorage()) { return false; }
    localStorage["halma.game.in.progress"] = gGameInProgress;
    for (var i = 0; i < kNumPieces; i++) {
	localStorage["halma.piece." + i + ".row"] = gPieces[i].row;
	localStorage["halma.piece." + i + ".column"] = gPieces[i].column;
    }
    localStorage["halma.selectedpiece"] = gSelectedPieceIndex;
    localStorage["halma.selectedpiecehasmoved"] = gSelectedPieceHasMoved;
    localStorage["halma.movecount"] = gMoveCount;
    return true;
}
```

[Back to Main](README.md)
