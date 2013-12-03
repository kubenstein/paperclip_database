Paperclip Database Storage
==========================

[![Build Status](https://secure.travis-ci.org/softace/paperclip_database.png)](http://travis-ci.org/softace/paperclip_database)
[![Dependency Status](https://gemnasium.com/softace/paperclip_database.png)](https://gemnasium.com/softace/paperclip_database)
[![Code Climate](https://codeclimate.com/github/softace/paperclip_database.png)](https://codeclimate.com/github/softace/paperclip_database)

Paperclip Database Storage is an additional storage option for
Paperclip. It give you the opportunity to store your paperclip binary
file uploads in the database along with all your other data.

Requirements
------------

`paperclip_database` depends on `paperclip`

It is recommended to use the
[trim_blobs](https://github.com/softace/trim_blobs) gem to limit the
logging of BLOB data in your logfiles.

Installation
------------

Paperclip Database Storage is distributed as a gem, which is how it
should be used in your app.

Include the gem in your Gemfile:

    gem "paperclip_database", "~> 2.0"

Or, if you want to get the latest, you can get master from the main
paperclip repository:

    gem "paperclip_database", :git => "git://github.com/softace/paperclip_database.git"
    
If you're trying to use features that don't seem to be in the latest
released gem, but are mentioned in this README, then you probably need
to specify the master branch if you want to use them. This README is
probably ahead of the latest released version, if you're reading it on
GitHub.

Supported Versions
------------------

As of version 2.0, Rails 2 is no longer supported.
Supported version are rails >= 3.0 and paperclip version >= 2.5

Quick Start
-----------

There is no quick start. You definitely need to understand how to use
paperclip first.

Usage
-----

You use `paperclip_database` by specifying `database` as storage for
your paperclip and create a migration for the additional database
table.

In your model:

    class User < ActiveRecord::Base
      has_attached_file :avatar, 
                        :storage => :database ## This is the essence
                        :styles => { :medium => "300x300>", :thumb => "100x100>" }
    end

There is a migration generator that will create a basic migration for
the extra table.

On the console (rails 3):

    rails generate paperclip_database:migration install

Development
-----------

To start develop, please download the source code

    git clone git://github.com/softace/paperclip_database.git

When downloaded, you can start issuing the commands like

    bundle install
    bundle exec rake appraisal:gemfiles
    bundle exec rake appraisal:install
    bundle exec rake all

Or you can see what other options are there:

    bundle exec rake -T

History
-------

Paperclip Database Storage is heavily inspired by [this blog by Pat
Shaughnessy](http://patshaughnessy.net/2009/2/19/database-storage-for-paperclip). The
initial source code for that blog is no longer available, but the code
in this gem is based on that initial code.



Copyright
---------

Copyright (c) 2012 Jarl Friis. See LICENSE.txt for
further details.

