
# nDistro

 Node distribution shell script. _nDistro_ allows you to build your own
 [node](http://nodejs.org) distribution using a simple configuration file, without 
depending on large programs. To contribute a node binary head over to [nodes](http://github.com/visionmedia/nodes).

## Installation

     $ cd /usr/local/bin && curl https://github.com/visionmedia/ndistro/raw/master/install | sh

## Example distribution

 A _nDistro_ is simply a dotfile named _.ndistro_ which defines
 module and node binary version dependencies. In the example
below we specify the node binary version _0.1.102_, as well as
several 3rd party modules.

	node 0.1.102
	module senchalabs connect
	module visionmedia express 1.0.0beta2
	module visionmedia connect-form
	module visionmedia connect-redis
	module visionmedia jade
	module visionmedia ejs

Follow the installation step above to gain access to the _ndistro_ executable,
and then in your distro directory that contains _.ndistro_ run:

    $ ndistro

## Sharing Distributions

To share distributions create a _.ndistro_ GitHub repository,
after which you can push several distributions, for some
examples view mine [here](http://github.com/visionmedia/.ndistro).

To list a user's distributions execute:

    $ ndistro visionmedia

To install one to the **CWD** run:

    $ ndistro visionmedia redis
or
    $ ndistro visionmedia express

## Updating A Library

Updating a library with nDistro is easy, first remove it:

    $ rm -fr modules/express

then execute `ndistro` again:

    $ ndistro

or if you wish to have a clean start and re-install everything:

    $ rm -fr bin modules && ndistro

## node <version>

  Specifies the _version_ of node to install.

    node 0.1.102

## module &lt;user&gt; &lt;project&gt; [version]
	
  Installs _user_'s _project_ at the given _version_ or **HEAD**.

    module visionmedia express
    module visionmedia express 1.0.0beta2

## Contributors

  - TJ Holowaychuk ([visionmedia](http://github.com/visionmedia))
  - Vladimir Dronnikov ([dvv](http://github.com/dvv))
  - Eric Clemmons ([ericclemmons](http://github.com/ericclemmons))

## License

(The MIT License)

Copyright (c) 2010 TJ Holowaychuk &lt;tj@vision-media.ca&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
