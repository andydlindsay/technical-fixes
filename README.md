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
