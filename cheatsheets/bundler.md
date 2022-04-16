# Bundler

## How to Update Gems

```bash
bundle update
```

The same as removing `Gemfile.lock` and running `bundle install`

```bash
bundle update GEM_NAME
```

Slightly more surgical, but will still upgrade all the dependencies on GEM_NAME


```bash
bundle update --conservative GEM_NAME
```

The most surgical and almost always how I want to update gems
