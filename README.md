Express & ES6 REST API Boilerplate
==================================

[![bitHound Score](https://www.bithound.io/github/developit/express-es6-rest-api/badges/score.svg)](https://www.bithound.io/github/developit/express-es6-rest-api)

This is a straightforward boilerplate for building REST APIs with ES6 and Express.

- ES6 support via [babel](https://babeljs.io)
- REST resources as middleware via [resource-router-middleware](https://github.com/developit/resource-router-middleware)
- CORS support via [cors](https://github.com/troygoode/node-cors)
- Body Parsing via [body-parser](https://github.com/expressjs/body-parser)

> Tip: If you are using [Mongoose](https://github.com/Automattic/mongoose), you can automatically expose your Models as REST resources using [restful-mongoose](https://git.io/restful-mongoose).

Getting Started
---------------

```sh
# clone it
git clone git@github.com:developit/express-es6-rest-api.git myEs2015Project && cd myEs2015Project

# Make it your own
rm -rf .git && git init && npm init -y

# Install dependencies
npm install

# Start development live-reload server
PORT=8080 npm run dev

# Start production server:
PORT=8080 npm start
```

## `npm` tasks

     "scripts": {
        "dev": "nodemon -w src --exec \"babel-node src --presets es2015,stage-0\"",
        "build": "babel src -s -D -d dist --presets es2015,stage-0",
        "start": "node dist",
        "prestart": "npm run -s build",
        "test": "eslint src"
      },


## Heroku Installation

- Install the [Heroku Toolbelt](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)
- Log at heroku:

```bash
    $ heroku login
    Enter your Heroku credentials.
    Email: juanma.garrido@gmail.com
    Password (typing will be hidden): 
    Logged in as juanma.garrido@gmail.com
```

### If you want to create a new app

    $  heroku create
    Creating sharp-rain-871... done, stack is cedar-14
    http://sharp-rain-871.herokuapp.com/ | https://git.heroku.com/sharp-rain-871.git
    Git remote heroku added

### If the app already exists

Just add as a remote repo

    $ git remote add heroku https://git.heroku.com/quiet-inlet-67115.git

## Heroku Deploy

Just commit to the heroku remote repo

    $ git push heroku master
    Counting objects: 343, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (224/224), done.
    Writing objects: 100% (250/250), 238.01 KiB, done.
    Total 250 (delta 63), reused 0 (delta 0)
    remote: Compressing source files... done.
    remote: Building source:
    remote:
    remote: -----> Node.js app detected
    remote:
    remote: -----> Creating runtime environment
    remote:
    remote:        NPM_CONFIG_LOGLEVEL=error
    remote:        NPM_CONFIG_PRODUCTION=true
    remote:        NODE_MODULES_CACHE=true
    remote:
    remote: -----> Installing binaries
    remote:        engines.node (package.json):  5.9.1
    remote:        engines.npm (package.json):   unspecified (use default)
    remote:
    remote:        Downloading and installing node 5.9.1...
    remote:        Using default npm version: 2.7.4
           ....
    remote: -----> Build succeeded!
    remote:        ├── ejs@2.4.1
    remote:        └── express@4.13.3
    remote:
    remote: -----> Discovering process types
    remote:        Procfile declares types -> web
    remote:
    remote: -----> Compressing... done, 9.4MB
    remote: -----> Launching... done, v8
    remote:        http://sharp-rain-871.herokuapp.com deployed to Heroku
    To https://git.heroku.com/nameless-savannah-4829.git
     - [new branch]      master -> master

## Heroku Logs

To see what's going on the remote server

    $ heroku logs
    2016-08-05T07:52:32.036514+00:00 heroku[router]: at=info method=GET path="/api/search/beers?q=ipa" host=quiet-inlet-67115.herokuapp.com request_id=0f5fbc67-e83b-469b-9736-2547979d124d fwd="80.33.152.186" dyno=web.1 connect=0ms service=570ms status=200 bytes=114341
    ...

## Troubleshooting

If you get error...

    ERROR in Cannot find module '../modules/web.dom.iterable'

You can try to do

    rm -rf node_modules && npm install

> Source: [curtismlarson.com](http://www.curtismlarson.com/blog/2016/05/12/webpack-cannot-find-module-web-dom-iterable/)