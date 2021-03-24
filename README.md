MimeMagic is a library to detect the mime type of a file by extension or by content. It uses the mime database
provided by freedesktop.org (see http://freedesktop.org/wiki/Software/shared-mime-info/).

[![Gem Version](https://img.shields.io/gem/v/mimemagic.svg)](http://rubygems.org/gems/mimemagic)

Usage
=====

```ruby
require 'mimemagic'
MimeMagic.by_extension('html').text?
MimeMagic.by_extension('.html').child_of? 'text/plain'
MimeMagic.by_path('filename.txt')
MimeMagic.by_magic(File.open('test.html'))
# etc...
```

You can add your own magic with `MimeMagic.add`.

API
===

http://www.rubydoc.info/github/minad/mimemagic

Tests
=====

```shell
bundle install

rake test
```

Contribution
===========

Update mimemagic table data
---------------------------

The following rake task will fetch the latest (or speficic release) data from
the [shared-mime-info](https://gitlab.freedesktop.org/xdg/shared-mime-info) project
and rebuilds the `mimemagic/table` data.

```shell
# Build table w/ most recent data
rake tables

# Build tables for specific `shared-mime-info` release
rake tables RELEASE="2.1"
```

Authors
=======

Daniel Mendler

LICENSE
=======

GPL-2.0
