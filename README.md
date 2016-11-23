[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

#jQuery HTML5 Uploader

jQuery HTML5 Uploader is a lightweight [jQuery plugin](http://plugins.jquery.com/) that lets you to quickly add an upload system [a-la-Gmail](http://googlesystem.blogspot.co.uk/2010/04/drag-and-drop-gmail-attachments.html) into your web app.

You only need to create a dropbox element (i.e. a div) and jQuery HTML5 Uploader will do the rest. Then you can drag & drop one or more files on the element and the files will be uploaded.

It also works with the [multiple input file element](http://www.w3.org/TR/html-markup/input.file.html).

The upload function is divided into two asynchronous operations: client side, the file is loaded in the browser memory with a [FileReader](https://developer.mozilla.org/en-US/docs/Web/API/FileReader) object. Useful if you want, for example, to show the image preview while uploading a picture. The server side operation consists in sending the binary file string to the postUrl (see settings).

It has been tested and works on [Firefox](https://www.mozilla.org/en-GB/firefox/new/) and [Chrome](http://www.google.com/chrome/).

#Usage

```html    
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5.2/jquery.min.js"></script>
<script type="text/javascript" src="js/jquery.html5uploader.min.js"></script>
<script type="text/javascript">
$(function() {
	$("#dropbox, #multiple").html5Uploader({
		name: "foo",
		postUrl: "bar.aspx"	
	});
});
</script>
<div id="dropbox"></div>
<input id="multiple" type="file" multiple>
```

#Settings

- `name`: upload field identifier.
- `postUrl`: the url to post the file data.
- `onClientAbort`: Called when the read operation is aborted.
- `onClientError`: Called when an error occurs.
- `onClientLoad`: Called when the read operation is successfully completed.
- `onClientLoadEnd`: Called when the read is completed, whether successful or not. This is called after either onload or onerror.
- `onClientLoadStart`: Called when reading the data is about to begin.
- `onClientProgress`: Called periodically while the data is being read.
- `onServerAbort`: Called when the post operation is aborted.
- `onServerError`: Called when an error occurs.
- `onServerLoad`: Called when the post operation is successfully completed.
- `onServerLoadStart`: Called when posting the data is about to begin.
- `onServerProgress`: Called periodically while the data is being posted.
- `onServerReadyStateChange`: A JavaScript function object that is called whenever the readyState attribute changes. The callback is called from the user interface thread.
- `onSuccess`: Called when the post operation is successfully completed, the ReadyState is 4 and the HttpStatus is 200. Useful to get back informations from the server.
