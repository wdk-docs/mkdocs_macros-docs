# Changelog: mkdocs-macros

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 0.7.0, 2022-03-25

* Added: (#133) `on_error_fail` in config file to make build/serve process
        fail in case of macro error, with return code 100.

* Added: (#130) Documentation on the tree structure of a typical 
         macro directory (package) 

## 0.6.4, 2022-01-27

* Fixed: (#118) `{{ git.date }}` is now committer date (no longer author date).
* Added: new git info elements (author email, committer, committer email); 
         documentation was updated
* Added: by default, unknown variables in a markdown page (`{{ foo }}`)
         are no longer replaced by blanks but displayed as is (DebugUndefined) (#117);
         for better compatibility with other plugins or error detection
* Added: `on_undefined` parameter in plugin definition to alter behavior 
         with unknown jinja2 variables: 'keep' (default), 'silent', 'strict', 'lax';
         documentation was updated

## 0.6.3, 2021-11-23

* Fixed: Broken build of 0.6.2

## 0.6.2, 2021-11-22 (yanked)

* Added: `env.raw_markdown` is now modifiable, for use in `on_post_page_macros()`

## 0.6.1, 2021-09-09

* Added: auto-install of pluglets (in `module` parameter in config file)

## 0.6.0, 2021-22-08

* Fixed: documentation (for readthedocs) now contains proper
         link to edit uri on github
* Fixed: broken link in webdoc/docs/pages.md
* Bump version to 0.6.0, to acknowledge the breaking change in 0.5.10

## 0.5.12, 2021-06-09

* Fixed: Incompatibility with mkdocs 1.2
         (`on_serve()` event, call to `server.watch()`)

## 0.5.11, 2021-04-24

* Added: Info on pluglets, on GitHub index page.
* Added: Contributing and Help pages, in documentation

## 0.5.10, 2021-04-23

Warning: Breaking Change

* Fixed: impossibility to use imported Jinja2 macros, without `with context`
    clause (#81). Now macros are imported as global.
* **Removed: Do not define macros as variables any longer, but as macros.**
    - incorrect: `env.variables['foo'] = foo` (though it should still work)
    - correct: prefix declaration with `@env.macros` 
      or `env.macros['foo'] = foo`
* Added: Changelog is also part of documentation
* Added: Documentation moved under Material them, slate variant (dark)
* Added: Amended documentation (test install, discussions)

## 0.5.9, 2021-04-22

* Added: Changelog (Fixed #82)


## 0.5.8, 2021-04-21

* Fixed: display better message in case of macro syntax error 
    (line_no, message, incriminated line in file).
    Traceback was useless with that specific exception, and has been removed.

## 0.5.7, 2021-04-21

* Added: Possibility (for large projects) to exclude a markdown page 
    from macro rendering, with `ignore_macros: true` in YAML header
    (fixed issue #78, and answered discussion #79)

## 0.5.6, 2021-04-19

* Added: Files object to the mkdocs-macros environment (fixed #80)
* Fixed: Documentation errors or omissions
* Fixed: Do not install pluglet mkdocs-macros-test by default (#50)
    In order to do testing, 
    type: `pip install 'mkdocs-macros-plugin[test]'`

## 0.5.5, 2021-03-03

* Starting point