davmail-docker
==============

[Davmail](http://davmail.sourceforge.net/) running inside [docker](http://docker.io).

Do you trust Java? Me either. Use this docker container to run davmail locally and connect to your Exchange email provider.

Usage
=====

Create your davmail config file:

    $ mkdir ~/.davmail
    $ vi ~/.davmail/davmail.properties #enter your davmail config here
    
You can either clone this and build your own image, or use my image created from this Dockerfile.

To use the image:

    $ docker pull gondoi/davmail
    $ docker run -d -v ~/.davmail:/etc/davmail gondoi/davmail
    
To tweak and build your own:

    $ docker build .
    $ docker run -d <imageid>
