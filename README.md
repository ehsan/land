# land
land is a sophisticated bot to auto-land your commits in the background.

### Setup
This tool assumes that you push to mozilla-inbound through git-cinnabar.
If you use git, you should consider doing that!

With that, you create a new git work-dir like this:

```
$ git new-workdir path/to/gecko-dev landing
```

And then you set up an inbound branch that is ready to push from.  Then, when
landing a patch, you switch to the landing directory, and do something like:

```
$ cd landing
$ git cherry-pick mycommitsha1
$ # maybe more of this!
$ land
```

And then switch away from that terminal.  If the process of rebasing your patch
in the case of a race gets into a problem, the tool errors out.
