Share and an API for Annotator Plugin
==================
##Share Annotator Plugin

share-annotator.js is a plugin for Annotator. This project has two objectives. On the one hand, to share with social networks (Google, Facebook, Twitter, email...). On the other hand, the annotations API to create a URL that open automatically the annotation, no matter if the annotation is not in the database.

The share plugin allow you to share text annotations and video annotations with Open Video Annotator. The code is written in javascript/jquery, but you can traslate to coffee using [js2coffee](http://js2coffee.org/), the language used in Annotator.

This plugin will be used in [Open Video Annotation tool](http://www.openvideoannotation.org/). 
A project supported by [Center for Hellenic Studies](http://chs.harvard.edu/), at [Harvard University](http://www.harvard.edu/) and the [Becas Talentia](http://www.juntadeandalucia.es/economiainnovacionyciencia/talentia/) program from the Junta de Andalucia, Spain.

##Live-Demo

There is a demo of the share annotation plugin in the next webpage:

http://danielcebrian.com/share-annotation/demo.html


##Installation

To use the tool you need to install the [Annotator plugin](https://github.com/okfn/annotator/) to annotate text. But if you want to annotate video you will need the [Open Video Annotation plugin](https://github.com/CtrHellenicStudies/OpenVideoAnnotation).

In addition add share-annotator.min.js and share-annotator.min.css CDN distributed file to your head tag, just after
videojs:

```html
	<head>
		<!-- Annotator -->
		<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7/jquery.min.js"></script>
		<script src="http://assets.annotateit.org/annotator/v1.2.7/annotator-full.min.js"></script>
		<link rel="stylesheet" href="http://assets.annotateit.org/annotator/v1.2.7/annotator.min.css">

		<!--Share Pluging-->
		<script src="build/share-annotator.min.js"></script>
		<link href="build/share-annotator.min.css" rel="stylesheet">
	
	</head>
```

Futhermore, you will need to create an instance of Annotator with the plugin, as follow:

```js
	<script>
    	$('#div_id').annotator().annotator('addPlugin','Share');
    </script>
```

Change #div_id for the real id where the Annotator is.

##Ways to share

There is two way to share an annotation. 

The first one is using an old stored annotation in the back-end with its id, the url will use "ovaId" to know the Id of the annotation.

The second one won't store the annotation and it will need the annotation parameters (ovaStart, ovaEnd and ovaText). 

For Text Annotation is necessary in addition:
 - ovastartOffset and ovaendOffset like annotator does with the text annotations

For Video Annotation is necessary in addition:
 - ovaContainer with the id of the video player
 - ovaSrc with the source url of the video to be loaded


##To-do

In the next version you can select the social network through options and add more using plugin options.
