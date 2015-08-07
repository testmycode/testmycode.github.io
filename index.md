---
layout: default
title: TestMyCode
---

Test My Code ("TMC") is a suite of tools that has been designed to make
the life of programming instructors and students easier, as well as
provide beneficial input for computing education researchers.

Instructors benefit from the automatic bookkeeping facilities as well as
the capability to build automated guidance into the programming
assignments. By crafting most of the issues that students face into the
tests as automated guidance, instructors can spend more face-to-face
time explaining and helping students with more difficult concepts.

Students benefit from Test My Code as it provides support for
downloading and submitting programming assignments directly from an IDE,
removing the unnecessary steps related to manually downloading and
uploading programming assignments. In addition, students' learning can
be more productive thanks to instructional scaffolding from the tests
within the programming assignments. When these two features are
combined, students simply can program more during a given time frame,
which is especially useful in introductory programming courses, where
large parts of the students' struggle is related to applying and
practising what they have just learned.

Researchers benefit from the data that is gathered from the students'
programming process. Test My Code provides a lightweight instrument for
tracking students' programming process on a key press by key press
-level. This provides unprecedented insight into the learning process.


The system has been used with great success by thousands of users at
universities such as the University of Helsinki and Aalto University. It
is also the tool that enables many of the MOOCs offered at
[http://mooc.fi](http://mooc.fi).


The code
All of the code is available under
[https://github.com/testmycode](https://github.com/testmycode)

The main components are:

* [The Server](https://github.com/testmycode/tmc-server)
* [The NetBeans plugin](https://github.com/testmycode/tmc-netbeans)
* [The User-mode Linux sandbox for running
submissions](https://github.com/testmycode/tmc-sandbox)

The current maintainers are [@mpartel](https://github.com/mpartel) and
[@jamox](https://github.com/jamox).

IRC: #testmycode @ Freenode

## Contributing
Great, you want to contribute! Welcome! :)

If you find a bug, please report it into the issues! Make sure that you
include steps that are needed to reproduce the bug -- this makes hunting
the bug down a lot more fun. In case of security issues or
vulnerabilities, don't disclose those in public or in our issue
trackers, but let the maintainers to know promptly.

If you have an idea for a new feature, we recommend that you discuss the
idea with the maintainers of TMC on IRC at #testmycode @ Freenode. This
helps you to avoid duplicate effort as your idea may be worked on
elsewhere as well -- if no one is working on that feature, we can point
you to the right component(s) for making the change.
Also before you start working on a larger contribution, you should get in
touch with us first through the issue tracker with your idea so that we
can help out and possibly guide you. Coordinating up front makes it much
easier to avoid frustration later on.

After that, just:

1. Create a GitHub issue (or more) that describes your idea. The issue
should be such that it can be completed based on the description.
Provide pictures if needed.
2. Find the correct repository that you are going to work with.
3. Set up a development environment as described in the README file of each
project. All projects can be developed with the latest Ubuntu LTS. Other
Linux distributions may require some fiddling with. Root permissions are
required.
4. Create a branch for your work. Use descriptive branch names.
5. Create a pull request from your branch, start with WIP:. Remember to
push changes frequently.
6. Write the solution into your branch. Make sure to provide automated
tests as well, and make sure that your tests cover your implementation
(see e.g. cobertura). Finally, check that your code follows the coding
conventions described later in this document.
7. Before submitting or updating a pull request, run the entire test suite.
(We know it takes ages to run but it does catch a lot of bugs.)
8. Let the reviewers know that your pull request is ready.

Make sure to update your pull request early and frequently to provide us
time to go through your changes and give feedback. When working on large
changes, do them in small iterations so that you can receive periodical
code reviews that can, if needed, also be merged at reasonable
checkpoints.

## Coding conventions
Mostly just try to stick to the style you see used in the project. Don't
introduce new dependencies if close to same can be accomplished with
existing dependency.

### Ruby
* Indentation: two spaces, no tabs.
* No trailing whitespace, even on blank lines.
* Indent before private/protected.
* Use Ruby >= 1.9 syntax for hashes. Prefer { a: :b } over { :a => :b }.
* Prefer && and \|\| over and and or.
* Prefer extend self over def self.method for modules.
* Write method calls like foo(bar, baz) (parenthesis may be omitted in
* very clear cases, but it is not required)
* Spaces around operators: a = b + c, not a=b+c.
* Single-line blocks should use braces like this: foo {\|x\| stuff(x) }.
* Multiline blocks should use do \|x\| syntax.

### Java
* Indentation: four spaces, no tabs.
* No trailing whitespace, even on blank lines.
* No blank lines after method definitions ifs, whiles etc.
* No unnecessary final attributes inside methods or for parameters
* Method calls have no space before or after paren: foo(bar, baz).
* Keywords have space before paren: if (foo) etc.
* In other matters, refer to
* [http://google-styleguide.googlecode.com/svn/trunk/javaguide.html](http://google-styleguide.googlecode.com/svn/trunk/javaguide.html)
unless
the surrounding code clearly and consistently disagrees.

### Javascript
* Indentation: two spaces, no tabs.
* No trailing whitespace, even on blank lines.
* Follow [http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml) unless the surrounding code clearly and consistently disagrees.
* Some files in the project may not completely adhere to the above
guidelines. Feel free to update any such files as you go.

## Reporting issues
It's best to report issues in the correct GitHub repository. If in
doubt, report to either the [tmc-server](https://github.com/tmc-server)
or the [tmc-netbeans](https://github.com/tmc-netbeans) repository.

Before reporting, please do a search to see if the issue has already
been reported.

Feature requests are also welcome in the issue tracker.

You are also very welcome to ask any questions or discuss ideas on IRC
at #testmycode @ Freenode.

## Testing a pull request
First, create a branch to merge the changes into:

```bash
$ git checkout -b testing_branch
```
Now merge their remote branch into your testing branch. For example,
let's say the GitHub user `jamox` has forked and pushed to a topic branch
"feature" located at https://github.com/jamox/tmc-server.

```bash
$ git remote add jamox git://github.com/jamox/tmc-server.git
$ git pull jamox feature
```

Remember to run database migrations and recompile things as necessary.

When you're done, switch back to the master branch and delete the
testing branch.

```bash
$ git checkout master
$ git branch -D testing_branch
```

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

      <h2>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </h2>
    </li>
  {% endfor %}
</ul>
