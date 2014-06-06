

##1\. 5 minutes tutorial

In this section we give the basic steps to get you started with your first Pillar document and exports\. You first need to create a *base directory* inside which we will put all your text, configuration files, and Pillar itself\.




    mkdir mydocument
    cd mydocument





###1\.1\. Installing and exporting your first document

You first need to download Pillar\. For that, I recommend executing [this script](https://raw2.github.com/SquareBracketAssociates/PharoForTheEnterprise-english/master/download.sh) in the base directory\.

Then, you can check everything is working fine by creating a `first.pier` file with this content:

&nbsp;


    !Hello World



And finally compiling it from a terminal \(see Section [¿?](#commandLineInterface) for more information about the command\-line interface\):

&nbsp;


    ./pillar export --to='html' 'first.pier' > first.html



This should generate a `first.html` file you can open in a web browser\. This content of this file will be something like:

&nbsp;


    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>No title</title>
        [...]
      </head>
      <body>
        <div class="container">
          <h1>Hello World</h1>
        </div>
        [...]
      </body>
    </html>





###1\.2\. Configuring a document

As you can see, there is no title in the generated `first.html` file\. This is because we did not specify any\. To specify a title, we have to write a configuration file\. This configuration is typically named `pillar.conf` and is written in the [STON](http://smalltalkhub.com/#!/~SvenVanCaekenberghe/STON) format \(see Section [¿?](#configuring) for more information about the configuration\)\. Create your first `pillar.conf` file:

&nbsp;


    {
        "title" : "My first document while reading the 5 minutes Pillar tutorial"
    }



When you compile using the same command line,

&nbsp;


    ./pillar export --to=html first.pier > first.html



you should now get a web page with a title:

&nbsp;


    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>My first document while reading the 5 minutes Pillar tutorial</title>
      </head>





###1\.3\. Exporting a different content using a template

If you want to tweak the content of the exported file, for example to reference your CSS or to add a footer, you need to create your own template \(see Section [¿?](#templating) for more information about templating\)\. You must write such template in its own file, e\.g\., `myhtml.template`:

&nbsp;


    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>{{{title}}}</title>
      </head>
      <body>
        <div class="container">
          {{{content}}}
        </div>
        <footer>
          <p>Damien Cassou, 2014</p>
        </footer>
      </body>
    </html>



Then, you need to reference this template from your configuration file\. So, edit your `pillar.conf` configuration file:

&nbsp;


    {
        "title" : "My first document while reading the 5 minutes Pillar tutorial",
        "configurations" : {
            "html" : {
                "template" : "myhtml.template",
                "outputType" : #html
            }
         }
    }



Now, compile `first.pier`

&nbsp;


    ./pillar export --to=html first.pier > first.html



to generate a `first.html` that will contain:

&nbsp;


    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>My first document while reading the 5 minutes Pillar tutorial</title>
      </head>
      <body>
        <div class="container">
          <h1>Hello World</h1>
        </div>
        <footer>
          <p>Damien Cassou, 2014</p>
        </footer>
      </body>
    </html>



This concludes our 5 minutes tutorial\.

