Laptop
======

Laptop is a pair of scripts to set up a macOS computer for web development.

We rely on [thoughtbot's script] for the heavy lifting and then make a few
additional customizations based on our own needs at Wellist. (There was a
[previous attempt] to fork our own copy, but that is not easy to maintain for
the very few customizations we need.)

It can be run multiple times on the same machine safely. It installs, upgrades,
or skips packages based on what is already installed on the machine. This is
not a fast process the first time it runs; go grab a coffee and a book.

[thoughtbot's script]: https://github.com/thoughtbot/laptop
[previous attempt]: https://github.com/Wellist/laptop-old

Install
-------

Download our customizations:

```sh
cd ~/
curl --remote-name https://raw.githubusercontent.com/Wellist/laptop/master/.laptop.local
```

Download the thoughbot script:

```sh
curl --remote-name https://raw.githubusercontent.com/thoughtbot/laptop/master/mac
```

Review our customizations and thoughtbot's script (avoid running scripts you
haven't read!):

```sh
less .laptop.local
less mac
```

Execute the downloaded script:

```sh
sh mac 2>&1 | tee ~/laptop.log
```

Optionally, review the log:

```sh
less ~/laptop.log
```

Debugging
---------

Your last run will be saved to `~/laptop.log`. Read through it to see if you can
debug the issue yourself. If not, copy the lines where the script failed into
our `#engineering` Slack channel, or if the error was in thoughtbot's script,
create a [new GitHub Issue](https://github.com/thoughtbot/laptop/issues/new) for
them. Or, attach the whole log file as an attachment.
