# Tool for transfering a config file from a raw resin image to another one

## Description
This repository enables building resin.io for various devices.

## Usage

```
    $ ./resin-f2t -h
```

## Example / use-case

### production / staging

The resin staging server is known to be a testing environment and due to this nature we happen to break it from time to time. On the other hand, we have users who want to get their hands on the new devices features as soon as possible.

Under the obvious notice that **this is ment to be used only in development and not in production**, we recommend these users to run resin staging images on the resin production server. Here is the way to do it:

1.  Download a staging image (dashboard.resinstaging.io).
2.  Download a production image (dashboard.resin.io) - make sure you currectly input the download configuration as this will the final config file used.
3.  $ ./resin-f2t --from production.img --to staging.img
4.  Use the staging.img for provisioning and the dashboard.resin.io for device manipulation.

### custom builds

There are cases when we want to run custom builds with resinio. This might happen for testing purposes for example. When finishing a build, the resulting artifact will not have a config. Injecting one from a already downloaded image can be done as follows:
1.  Download a staging image (dashboard.resinstaging.io).
2.  $ ./resin-f2t --from staging.img --to build-image-artifact.img
3   Use the build-image-artifact.img for provisioning and the dashboard.resinstaging.io for device manipulation.
