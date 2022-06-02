# W1 Exam Fixes

#### For those with an M1 and installation problems, follow the following instructions, if you don't have any issues, ignore this message!

```
brew install pyenv
pyenv install 3.9.10
pyenv global 3.9.10

echo -e 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo -e 'export PATH="$PYENV_ROOT/shims:$PATH"' >> ~/.zprofile
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zprofile
```

# W5 Exam Fixes

### Cannot install sqlite3 (or python) on Ubuntu

```
alias python=python2
npm config set python python2
npm i
```

### Cannot install sqlite3 on M1

```
brew install python@3.9
ln -s /opt/homebrew/bin/python3 /opt/homebrew/bin/python

nvm install 16
npm install -g @mapbox/node-pre-gyp
npm install --no-bin-links
```

* Or

```
npm install -g @mapbox/node-pre-gyp
brew install sqlite
npm install sqlite3 --build-from-source --sqlite=/opt/homebrew/opt/sqlite --save
```

# Vagrant Issues

### Issues running cypress on vagrant, please follow these steps:

```sh
# Update Ubuntu packages
$ sudo apt-get update

# Install dependencies for Ubuntu:
$ sudo apt-get install libgtk2.0-0 libgtk-3-0 libgbm-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb

# Exit vagrant
$ exit

# Connect back to vagrant
$ vagrant ssh

# Go back to your jungle folder
$ cd path/to/your/jungle

# Run Cypress in CI mode
$ bin/rails cypress:run

# Screenshots of failed attempts and videos will be in the tmp/  folder of your Jungle !
```

### Rails server won't reload when files change

```rb
# Add the following to config/environments/development.rb

# config.file_watcher = ActiveSupport::EventedFileUpdateChecker
config.file_watcher = ActiveSupport::FileUpdateChecker

# FileUpdateChecker will detect by polling the change of the file.
```
