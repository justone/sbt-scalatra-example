# To deploy to dotcloud

## 1. [Create an account](https://www.dotcloud.com/accounts/register/) and [set up the dotcloud utility](http://docs.dotcloud.com/firststeps/install/).

    $ pip install dotcloud

    $ dotcloud
    Enter your api key (You can find it at http://www.dotcloud.com/account/settings): xxxxxxxxxxxxxx

## 2. Build and push the war

    $ sbt clean package-war
    ... snip ...
    [info] Packaging /home/user/sbt-scalatra-example/target/scala-2.9.1.final/sbt-scalatra-example.war ...
    [info] Done packaging.
    [success] Total time: 13 s, completed Sep 23, 2011 3:57:00 PM

    $ cp target/scala-2.9.1.final/sbt-scalatra-example.war dotcloud/ROOT.war

    $ dotcloud create sbtscalatra
    Created application "sbtscalatra"

    $ cd dotcloud && dotcloud push sbtscalatra
    ... snip ...
    Deployment finished. Your application is available at the following URLs
    www: http://sbtscalatra-xxx.dotcloud.com/
