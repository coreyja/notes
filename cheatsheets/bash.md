# Bash

## Bash Script Shebang

```bash
#!/usr/bin/env bash
```

## Find/Replace in Directory

```bash
find ./ -type f -name "*.yml" -exec sed -i s'/thing1/thing2/g' {} \\;
```

## Git Pull in each Sub Dir

```bash
for dir in $(ls); do
    if [[ -d $dir ]]; then
        pushd $dir
            git pull --ff-only
        popd
    fi
done
```

## Bundle install if necessary in each sub-dir

```bash
for dir in $(ls); do
    if [[ -d $dir ]]; then
        pushd $dir
            [[ -f "./Gemfile" ]] && (bundle check || bundle install)
        popd
    fi
done
```

## pushd/popd - Got to a directory then return to current after

```bash
pushd ~/src/some-dir
    rake db:reset
popd
```

### Work in git root dir

```bash
pushd $(git rev-parse --show-toplevel)
  echo 'Do work here'
  pwd
popd
```

## Name and Shame for number of open branches

```bash
git branch -r | awk -F/ '{print $2}' | sort | uniq -c | sort -k1nr | head
```

## Run last command until it fails

```bash
while !!; do :; done
```

## Run a Command for each Installed version of Ruby

```bash
for version in $(rbenv versions --bare); do
    rbenv shell $version
    sudo gem update --system
done
rbenv shell --unset
```

## Run rubyfmt on all ruby files

```bash
for file in $(find . -type f -name "*.rb"); do rubyfmt "$file" > “${file}.tmp"; mv "${file}.tmp” “$file”; done
```

## Curl that reports failures as an exit code without output

```bash
curl -fsL $URL -o /dev/null
```

### Use Previous Arguments

`!$` uses the last argument from the previous command

Ex:

```bash
mv tmp.log tmp/
ls !$
```

`!*` gets ALL the previous args

```bash
# Typoed Command name
rpsec ~/some_file_spec.rb ~/other_file_spec.rb
rspec !*
```

More Ways to grab args

```bash
echo !:2 # Grab just the second arg from the last command
echo !1:3 # Grab the first, second and third arg
```
