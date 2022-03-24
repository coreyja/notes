# Bash

#### Find/Replace in Directory

```bash
find ./ -type f -name "*.yml" -exec sed -i s'/thing1/thing2/g' {} \\;
```

#### Git Pull in each Sub Dir

```bash
for dir in $(ls); do
    if [[ -d $dir ]]; then
        pushd $dir
            git pull --ff-only
        popd
    fi    
done
```

#### Bundle install if necessary in each sub-dir

```bash
for dir in $(ls); do
    if [[ -d $dir ]]; then
        pushd $dir
            [[ -f "./Gemfile" ]] && (bundle check || bundle install)
        popd
    fi    
done
```

#### pushd/popd - Got to a directory then return to current after

```bash
pushd ~/src/some-dir
    rake db:reset
popd
```

#### Name and Shame for number of open branches

```bash
git branch -r | awk -F/ '{print $2}' | sort | uniq -c | sort -k1nr | head
```

#### Run last command until it fails

```bash
while !!; do :; done
```

#### Run a Command for each Installed version of Ruby

```bash
for version in $(rbenv versions --bare); do
    rbenv shell $version
    sudo gem update --system
done
rbenv shell --unset
```

#### Run rubyfmt on all ruby files

```bash
for file in $(find . -type f -name "*.rb"); do rubyfmt "$file" > “${file}.tmp"; mv "${file}.tmp” “$file”; done
```

#### Curl that reports failures as an exit code without output

```bash
curl -fsL $URL -o /dev/null
```
