<link href="http://kevinburke.bitbucket.org/markdowncss/markdown.css" rel="stylesheet"></link>

Software Sharing Guidelines 
===========================

Social Computing Group, MIT Media Lab
------------------------------

Why?
----

A program that's **easy for everyone to run** will generate far more ideas
and improvements than one that is private. A program that only you can
run will likely die when you move on to something else.

Not every program is long-lived --- many programs are just quick
experiments. But when an experiment turns out useful or interesting,
it's worth spending the effort to share it and help it live on.

Adding another change to demonstrate git.

Adding some stuff here.

How, in Brief
-------------

Use this checklist:

- Source code is stored at Github.
- Source code contains a README file.
- Your dependencies are either:
  - automatically installable with the relevant package management
    tool,
  - copied directly into your repository,
  - or listed in the README, with version numbers and URLs.
- A new user who reads the README can successfully launch the program without editing it.
- Any input data that's needed is either:
  - stored directly alongside the source code, in which case:
    - the README should mention the data's provenance
    - and any program that post-processed the data should be part of the
      repository --- it's just as important as the "main" program.
  - or linked via URL from the README.
- Any account credentials that are needed (like Google Maps API keys)
  are explained in the README and can be passed as arguments.


How, in Detail
--------------

### Practice Empathy

Start by putting yourself in the mindset of someone who just
discovered your program for the first time. Help them decide whether
they want to run it. Help them get it running.

### Use Source Control

Your program should be stored in a Github repository. Either in a
public (to the world) repository, or in a private repository within
the Social Media Github organization.

Even simple projects that you aren't sharing with anyone else yet
benefit immensely from source control ("why did my program work
yesterday but not today?"). *Strongly* consider using source control
from the very beginning.

If you are not comfortable with [git](http://git-scm.com/), please ask
for help right away --- it's a skill very much worth acquiring.

### Create a Simple "README" File

Write at least a few sentences that explain why you created this
program, what it can currently do, and how to make it run.

> If "how to make it run" is long and complicated, don't write long
> and complicated instructions --- spend the time making your program
> easier to run instead.

In addition to the obvious benefit for a user who just discovered your
program, this also helps make your program discoverable. Consider what
keywords can appear in your README so that a future user can search
and find it.

### Track Dependencies

You created and tested your program under a particular
environment. A big headache for a future software archaeologist is
rediscovering what that environment was. 

At a minimum, explain your dependencies in the README. If it's
web-browser-based software, what browser(s) did you use?  For
example:

> "This was tested under Chrome 31 on Mac."

If your program depends on a local language runtime (Python, Ruby,
Processing, etc), list that:

> "Written for Ruby 2.0.0p195"

If you depend on any extra libraries that don't come built in to your
language, at a minimu you should list them in the README with version
numbers and URLs. But consider the following two options that are
easier for your users.

#### "Vendored" Dependencies

One simple way to help your users get the right dependencies is to
save them directly into your source repository. This can work well for
simple things, especially in purely-interpreted languages like
Javascript.

It's often referred to as "vendoring" because the conventional place
to put the libraries is in a folder named "vendor".

#### Automated Dependency Management

The best way to help your future users get running easily is to
use automatic dependency management, so they can install all the
proper libraries with a single command. This will manage not only
your dependencies, but your dependencies' dependencies, etc.

- In Ruby, use [Bundler](http://bundler.io/) and save the
  `Gemfile` and `Gemfile.lock` files in your source repository.

- In Python, use [pip](http://www.pip-installer.org/en/latest/)
  and save the `requirements.txt` file in your source repository.

- In Java, use [Ant](https://ant.apache.org/) or
  [Maven](https://maven.apache.org/) or
  [Gradle](http://www.gradle.org/).

- In server-side Javascript (NodeJS) use [npm](https://npmjs.org/).

- Client-side Javascript is still a wild frontier and there's no solid
  standard. [Bower](https://github.com/bower/bower) was written by
  Twitter and is a leading contender. Or you can combine npm and
  [browserify](https://github.com/substack/node-browserify).


### Configurability

You may be in the habit of directly editing your program to change
simple options. But this is not friendly for your users. Instead, make
your program accept arguments or read a configuration file.

### Data

Many of our programs (especially maps) are useless without very
specific input data. Your future users should not only be able to get
the data you used and run the program in the same way -- they should
be empowered to run your program with new data.

When possible, include the data within the source code repository and
document where it came from. If you processed the data with a program,
that program needs to be in the repository and documented just as well
as the "main" program.

If the data is too large to practically include with the source,
explain how to get it.

If getting the data depends on having specific account credentials
(like an API key), explain how to get credentials.

### New Section

I'm adding a new section to demonstrate git.

