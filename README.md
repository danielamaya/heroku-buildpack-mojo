Heroku buildpack: Mojolicious
======================

This is a Heroku buildpack that runs any Mojolicious based web applications using Hypnotoad.

Usage
-----

Example usage:

    $ ls
    cpanfile
    lib
    log
    mojo
    public
    script
    t
    templates

    

    $ cat cpanfile
    requires 'Plack', '1.0000';
    requires 'DBI', '1.6';

    $ heroku create --stack cedar --buildpack https://github.com/miyagawa/heroku-buildpack-perl.git

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> Perl/Mojo app detected
    -----> Installing dependencies

The buildpack will detect that your app has an `app.psgi` in the root.

Libraries
---------

Dependencies can be declared using `cpanfile` (recommended) or more traditional `Makefile.PL`, `Build.PL` and `META.json` (whichever you can install with `cpanm --installdeps`), and the buildpack will install these dependencies using [cpanm](http://cpanmin.us) into `./local` directory.
