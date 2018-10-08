# heroku18-buildpack-opencv-nodejs-bootstrap

[![Build Status](https://travis-ci.com/Starkast/heroku-buildpack-cmake.svg?branch=master)](https://travis-ci.com/Starkast/heroku-buildpack-cmake)

This buildpack contains neccessary files and install packages from Arch Linux to make opencv.js from NodeJs runs on Heroku-18 stack.
This is only the boostrap package. Put this as first in your buildpack.

In order to install full opencv.js dependencies.
   - Add the [APT buildpack](https://github.com/heroku/heroku-buildpack-apt) by Heroku (after this bootstrap buildpack).
   - Make an **Aptfile** in the root directory of your Git repo. 
   - Add these packages to your APT file:
```
    openexr
    libopenexr22
    libopencv-dev
    libcairo2-dev
    libcairo-gobject2
    libpng12-0
    libusb-dev
    ffmpeg
    libilmbase12
    liblapack-dev
    libatlas-base-dev
    g++-7
    libgfortran-8-dev
```
   - Test it out. Should be running fine.
   - In the end, the buildpacks should have ordered like this:
   ![Order](https://cdn.discordapp.com/attachments/463217723934113795/498864531532021760/unknown.png)

Usage:
    
    heroku buildpacks:set https://github.com/pent0/heroku18-buildpack-opencv-nodejs-bootstrap

See the Heroku documentation for more information:

* [Buildpacks]
* [Using Multiple Buildpacks for an App](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app)
* [Heroku Buildpack Registry](https://devcenter.heroku.com/articles/buildpack-registry)

[Buildpacks]: https://devcenter.heroku.com/articles/buildpacks
