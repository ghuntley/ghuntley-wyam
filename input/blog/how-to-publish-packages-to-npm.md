---
Title: How to publish packages to NPM
Published: 2016-01-02
Tags:
  - npm
  - javascript
  - package-management
---

If you haven't already set your NPM author info, here's how you do it

    # npm set init.author.name "Your Name"
    # npm set init.author.email "you@example.com"
    # npm set init.author.url "http://yourblog.com"

Login to NPM and obtain your publish token

    # npm adduser

Next steps are to create your `package.json`

    # cd /path/to/your-project
    # npm init

If you took on dependencies, then you should install and run pakmager

    # npm install -g pakmanager
    # pakmanager deps

Edit your package.json and add any deps you forgot about

    # vim package.json

Publish your library

    # npm publish ./ --tag beta
    # npm publish ./

Additional reading:

 * http://npmjs.org/doc/json.html
 * http://npmjs.org/doc/developers.html
 * http://blog.izs.me/post/1675072029/10-cool-things-you-probably-didnt-realize-npm-could-do
