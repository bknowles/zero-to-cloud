# Overview

Welcome to Zero to Cloud in 90 Days with Chef, based on the training
material for the class Chef Fundamentals by Opscode.  The materials
themselves are written in plain text
"[Markdown](http://daringfireball.net/projects/markdown/)" format,
and presented using the "[ShowOff](https://github.com/schacon/showoff)"
Ruby-based presentation application.

The rest of this file is largely carried over unchanged.

If you're seeing this at http://localhost:9090, you need to run the
`showoff` command from the `slides` directory.

# Setup

Requirements:

* Ruby 1.8.7+
* RubyGems 1.3.7+
* Rake
* libxml2 and libxslt development headers (e.g., libxml2-dev and
  libxslt-dev on Debian/Ubuntu).

```
gem install bundler
bundle install
rake present # runs bundle exec showoff serve in the slides dir
```

Depending on how your local system's Ruby was installed, you may need
to use `sudo` to run `gem install` and `bundle install`. You may also
need to use `bundle exec showoff serve` in the `slides` directory to
run the presentation, though the rake task should handle this already.

Two URLs are available:

* [http://localhost:9090](http://localhost:9090) - "student" view of the slides
* [http://localhost:9090](http://localhost:9090) - "presenter" view of the slides

When presenting the materials as an instructor, use the "presenter"
view. This will also pop up a second browser window that will advance
with the presenter window. To move forward and back, use the arrow
keys. Down/Right go forward, Up/Left go backward. Spacebar will also
advance slides forward.

# Installed Gems

The source materials in the `slides` directory are set up as a showoff
project. As such, the `showoff` gem is required. In order to generate
PDFs with showoff, the `pdfkit` gem is installed.

# Slides Directory

Most of the action happens in the slides directory.

## Slide Style Guide

This is spartan and will be embellished.

* Create sections as directories.
* Use PNGs for images.
* Directory names should be lower case words as a title, "getting-started"
* Each directory should have a 01_slide.md, multiple sections may be
  broken up later.

# Guides Directory

See the `instructor-setup.md` guide in the guides directory for
information on how to set up the lab environments for students to use
in the hands on portion of the course.

# Resources

[http://daringfireball.net/projects/markdown/syntax](http://daringfireball.net/projects/markdown/syntax)
[https://github.com/schacon/showoff](https://github.com/schacon/showoff)

# Contributing

See CONTRIBUTING for information on how you can contribute changes to
these materials.

# License and Authors

See LICENSE for licensing of these materials and how you may use
them.

## Authors:

Joshua Timberman <joshua@opscode.com>
Aaron Peterson <aaron@opscode.com>
Brad Knowles <bknowles@ihiji.com>
