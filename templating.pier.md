

##1\.  Templating
<a name="templating"></a>
Pillar comes with the [Mustache](http://smalltalkhub.com/#!/~NorbertHartl/Mustache) templating engine\. This means you can specify a preamble and postamble for your document\. Here is an example \(bootrap\-based\) HTML template using Mustache:




    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>{{{title}}}</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet">
        <link href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap-theme.min.css" rel="stylesheet">
        <link rel="stylesheet" href="http://yandex.st/highlightjs/8.0/styles/default.min.css">
        <script src="http://yandex.st/highlightjs/8.0/highlight.min.js"></script>
    
        <!--[if lt IE 9]>
          <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>
          <script src="https://oss.maxcdn.com/libs/respond.js/1.3.0/respond.min.js"></script>
        <![endif]-->
      </head>
      <body>
    
        <div class="container">
          {{{content}}}
        </div>
    
        <script src="https://code.jquery.com/jquery.js"></script>
        <script src="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js"></script>
        <script>hljs.initHighlightingOnLoad();</script>
      </body>
    </html>



In this example, we can see the use of `{{{title}}}` and `{{{content}}}` to refer to the title of the document and its actual content \(the one exported from Pillar\)\. You have to put such a template in a dedicated file \(named `chapter.html.template` for example\) and reference this file from the template configuration parameter \(see [¿?](#sec:confParam:template)\)\.
