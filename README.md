davmail-docker
==============

[Davmail](http://davmail.sourceforge.net/) running inside [docker](http://docker.io).

Do you trust Java? Me either. Use this docker container to run davmail locally
and connect to your Exchange email provider.

Usage
=====

The following usage instructions assumes Docker `>= 0.5.3` and your running
user in the `docker` system group (to prevent needed `sudo` usage).

Create your davmail config file, you can find a sample on the
[davmail site](http://davmail.sourceforge.net/serversetup.html).
Ports here need to match the ports in the `Dockerfile`, or you will need to
open your own ports during the `docker run`.

    $ mkdir ~/.davmail
    $ vi ~/.davmail/davmail.properties #enter your davmail config here
    
You can either clone this and build your own image, or use my image created
from this Dockerfile.

To use the image:

    $ docker pull gondoi/davmail
    $ docker run -d -v ~/.davmail:/etc/davmail gondoi/davmail
    
To tweak and build your own:

    $ docker build .
    $ docker run -d <imageid>
