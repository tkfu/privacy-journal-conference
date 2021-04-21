# Privacy journal conference website

This site is built in Jekyll using the [Business Jekyll Theme](https://business-jekyll-theme.github.io).

## Building and developing

You'll need Ruby (tested with 2.7.2, but probably anything 2ish will work).

First, set up your environment with `bundle install`

Then, you can build and serve the site locally using jekyll: `bundle exec jekyll s`

## Committing changes to git

### Adding files

When you've changed something and you're happy with it, you should commit your changes to git. Think of it like setting a save point.

If you've added any new files, you'll need to tell git to start tracking them with `git add`. This will add everything in the whole directory:

    git add .

This will add a single file:

    git add path/to/my/file.html

### Creating a commit

`git commit` creates a commit with the files you've added. You can also tell it to automatically add any files you've changed with the `-a` option, and you can specify a commit message with the `-m` option.

The most common way to do it is this:

    git commit -a -m 'a commit message describing your changes'

Note the single quotes enclosing the commit message. That means you can't have single quotes in the commit message unless you ask google how to do it first.

### Pushing to github

Once you've committed your changes locally, you can push to github so it's backed up and othe collaborators can work on it:

    git push origin master


## Publishing

The actual site is at https://privacystudies.org/, and it's hosted by one.com. To push a new version of the site, you should first build the site using `bundle exec jekyll b`, then use an SFTP client to copy the contents of the `_site/` directory to the privacy studies account. You can do that with the command line sftp client like this (from the privacy-journal-conference directory):

    sftp privacystudies.org@ssh.privacystudies.org

After entering the password, you should see the `sftp>` prompt. Type or paste the following:

    put -pR _site/*

That's it!

