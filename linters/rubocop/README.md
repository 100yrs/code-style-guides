# Common configuration for rubocop in TED projects

## Goals

Hold a common base configuration which should apply to all 100Years Ruby projects. Individual projects may further extend this, but generally the fewer exceptions we define the better.

## Usage

in your project's `.rubocop.yml`:

```yaml
inherit_from:
  - https://raw.githubusercontent.com/SesoMedia/code-style-guides/master/linters/rubocop/rubocop.yml
  - .rubocop_todo.yml # if you have one
```

The [Rubocop README](https://github.com/bbatsov/rubocop) has more details on how the file is sourced & updated. Essentially, it will be downloaded to your machine & used. Rubocop has some rules about updating the local copy when the remote file changes. You can also remove your local version (which will be in a `./rubocop-http*` file) to force an update to the latest.

**NOTE**: Support for sourcing config from URLs was added in Rubocop 0.35.0. In older versions you'll see no such file or directory @ rb_sysopen errors when starting Rubocop.

## Conventions in `rubocop.yml`

* Rubocop configuration options are listed here - https://github.com/bbatsov/rubocop/blob/master/config/default.yml
* Make a branch & open a PR when you want to change something in here. Then the git history & closed PRs become documentation about how our styles have evolved over time.
* Keep configs in the same order as the default configuration file.
* Include comments explaining why a particular configuration is here.
