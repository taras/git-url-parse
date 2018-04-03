<!-- Please do not edit this file. Edit the `blah` field in the `package.json` instead. If in doubt, open an issue. -->


[![git-url-parse](http://i.imgur.com/HlfMsVf.png)](#)

# git-url-parse

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Ask me anything](https://img.shields.io/badge/ask%20me-anything-1abc9c.svg)](https://github.com/IonicaBizau/ama) [![Travis](https://img.shields.io/travis/IonicaBizau/git-url-parse.svg)](https://travis-ci.org/IonicaBizau/git-url-parse/) [![Version](https://img.shields.io/npm/v/git-url-parse.svg)](https://www.npmjs.com/package/git-url-parse) [![Downloads](https://img.shields.io/npm/dt/git-url-parse.svg)](https://www.npmjs.com/package/git-url-parse)

> A high level git url parser for common git providers.

## :cloud: Installation

```sh
# Using npm
npm install --save git-url-parse

# Using yarn
yarn add git-url-parse
```


## :clipboard: Example



```js
// Dependencies
const GitUrlParse = require("git-url-parse");

console.log(GitUrlParse("git@github.com:IonicaBizau/node-git-url-parse.git"));
// => {
//     protocols: []
//   , port: null
//   , resource: "github.com"
//   , user: "git"
//   , pathname: "/IonicaBizau/node-git-url-parse.git"
//   , hash: ""
//   , search: ""
//   , href: "git@github.com:IonicaBizau/node-git-url-parse.git"
//   , token: ""
//   , protocol: "ssh"
//   , toString: [Function]
//   , source: "github.com"
//   , name: "node-git-url-parse"
//   , owner: "IonicaBizau"
// }

console.log(GitUrlParse("https://github.com/IonicaBizau/node-git-url-parse.git"));
// => {
//     protocols: ["https"]
//   , port: null
//   , resource: "github.com"
//   , user: ""
//   , pathname: "/IonicaBizau/node-git-url-parse.git"
//   , hash: ""
//   , search: ""
//   , href: "https://github.com/IonicaBizau/node-git-url-parse.git"
//   , token: ""
//   , protocol: "https"
//   , toString: [Function]
//   , source: "github.com"
//   , name: "node-git-url-parse"
//   , owner: "IonicaBizau"
// }

console.log(GitUrlParse("https://github.com/IonicaBizau/git-url-parse/blob/master/test/index.js"));
// { protocols: [ 'https' ],
//   protocol: 'https',
//   port: null,
//   resource: 'github.com',
//   user: '',
//   pathname: '/IonicaBizau/git-url-parse/blob/master/test/index.js',
//   hash: '',
//   search: '',
//   href: 'https://github.com/IonicaBizau/git-url-parse/blob/master/test/index.js',
//   token: '',
//   toString: [Function],
//   source: 'github.com',
//   name: 'git-url-parse',
//   owner: 'IonicaBizau',
//   organization: '',
//   ref: 'master',
//   filepathtype: 'blob',
//   filepath: 'test/index.js',
//   full_name: 'IonicaBizau/git-url-parse' }

console.log(GitUrlParse("https://github.com/IonicaBizau/node-git-url-parse.git").toString("ssh"));
// => "git@github.com:IonicaBizau/node-git-url-parse.git"

console.log(GitUrlParse("git@github.com:IonicaBizau/node-git-url-parse.git").toString("https"));
// => "https://github.com/IonicaBizau/node-git-url-parse.git"
```



## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:

 3. For direct and quick help, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:



## :memo: Documentation


### `gitUrlParse(url)`
Parses a Git url.

#### Params

- **String** `url`: The Git url to parse.

#### Return
- **GitUrl** The `GitUrl` object containing:
 - `protocols` (Array): An array with the url protocols (usually it has one element).
 - `port` (null|Number): The domain port.
 - `resource` (String): The url domain (including subdomains).
 - `user` (String): The authentication user (usually for ssh urls).
 - `pathname` (String): The url pathname.
 - `hash` (String): The url hash.
 - `search` (String): The url querystring value.
 - `href` (String): The input url.
 - `protocol` (String): The git url protocol.
 - `token` (String): The oauth token (could appear in the https urls).
 - `source` (String): The Git provider (e.g. `"github.com"`).
 - `owner` (String): The repository owner.
 - `name` (String): The repository name.
 - `ref` (String): The repository ref (e.g., "master" or "dev").
 - `filepath` (String): A filepath relative to the repository root.
 - `filepathtype` (String): The type of filepath in the url ("blob" or "tree").
 - `full_name` (String): The owner and name values in the `owner/name` format.
 - `toString` (Function): A function to stringify the parsed url into another url type.
 - `organization` (String): The organization the owner belongs to. This is CloudForge specific.
 - `git_suffix` (Boolean): Whether to add the `.git` suffix or not.

### `stringify(obj, type)`
Stringifies a `GitUrl` object.

#### Params

- **GitUrl** `obj`: The parsed Git url object.
- **String** `type`: The type of the stringified url (default `obj.protocol`).

#### Return
- **String** The stringified url.



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:


 - Starring and sharing the projects you like :rocket:
 - [![Buy me a book][badge_amazon]][amazon]—I love books! I will remember you after years if you buy me one. :grin: :book:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)


Thanks! :heart:


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`autorelease-setup`](https://github.com/tyler-johnson/autorelease-setup#readme) (by Tyler Johnson)—A CLI tool for setting up a repository with autorelease.
 - [`belt-repo`](https://npmjs.com/package/belt-repo) (by ewnd9)—repo module for belt
 - [`bibi`](https://github.com/steelbrain/bibi#readme) (by steelbrain)—A repository management tool
 - [`branch-release`](https://github.com/RomanGotsiy/branch-release#readme) (by Roman Hotsiy)—Build and tag package realease on a separate branch
 - [`changelog.md`](https://github.com/egoist/changelog.md#readme) (by EGOIST)—Manage CHANGELOG.md so easy it hurts.
 - [`ci-yarn-upgrade`](https://github.com/taichi/ci-yarn-upgrade) (by taichi)—Keep NPM dependencies up-to-date with CI, providing version-to-version diff for each library
 - [`clipped`](https://github.com/clippedjs/clipped#readme) (by IniZio)—Reduce pain of configuration to once
 - [`committing`](https://github.com/axetroy/committing#readme) (by Axetroy)—commit every days
 - [`complan`](https://github.com/pranavparikh/complan#readme) (by Pranav Parikh)—COMPLexity ANalyzer Tool For Javascript
 - [`def-core`](https://npmjs.com/package/def-core) (by tbfed)—def core for deflite
 - [`docula-ui`](https://npmjs.com/package/docula-ui)—Express.js bindings for Docula project
 - [`docula-ui-express`](https://npmjs.com/package/docula-ui-express)—Express.js bindings for Docula project
 - [`documentation`](https://github.com/documentationjs/documentation#readme) (by Tom MacWright)—a documentation generator
 - [`documentation-fork`](https://github.com/documentationjs/documentation#readme) (by Tom MacWright)—a documentation generator
 - [`documentation-habitlab`](https://github.com/documentationjs/documentation#readme) (by Tom MacWright)—a documentation generator
 - [`download-repo-cli`](https://github.com/egoist/download-repo-cli#readme) (by EGOIST)—CLI tool to download GitHub repo.
 - [`gd-cli`](https://npmjs.com/package/gd-cli) (by Sylvain Baronnet)—GD Command Line Interface
 - [`generator-ckeditor4`](https://github.com/mlewand/generator-ckeditor4#readme) (by Marek Lewandowski)—Yeoman generator for CKEditor 4
 - [`generator-clearphp`](https://github.com/jkphl/generator-clearphp#readme) (by Joschi Kuphal)—Scaffold for Composer based PHP projects with a lot of integrations, advocating the use of The Clear Architecture (https://jkphl.is/articles/clear-architecture-php)
 - [`generator-nm-bti`](https://gitlab.com/beneaththeink/generator-nm-bti#README) (by Tyler Johnson)—Scaffold out a node module, Beneath the Ink style.
 - [`generator-openapi-repo`](https://github.com/Rebilly/generator-openapi-repo#readme) (by Roman Hotsiy)—Yeoman generator for OpenAPI(fka Swagger) repo to help you share spec for your API
 - [`git-cherry-fix`](https://npmjs.com/package/git-cherry-fix)—> helps you get your fixes to another branch by cherry-picking them
 - [`git-issues`](https://github.com/softwarescales/git-issues) (by Gabriel Petrovay)—Git issues extension to list issues of a Git project
 - [`git-lab-cli`](https://npmjs.com/package/git-lab-cli)—gitlab-cli ==================
 - [`git-signed`](https://github.com/Wizcorp/git-signed#readme) (by Marc Trudel)—git commit signing made easy (and enforceable)
 - [`git-source`](https://github.com/IonicaBizau/git-source#readme)—Parse and stringify git urls in a friendly way.
 - [`git-url-promise`](https://github.com/joshuan/git-url#readme) (by Evgeniy Shershnev)—Git url promise
 - [`gitbook-start-https-alex-moi`](https://github.com/ULL-ESIT-SYTW-1617/https-al-servidor-del-libro-alex-moi.git#readme) (by Moises Yanes Carballo)—Plugin deploy iaas https
 - [`gitbook-start-iaas-bbdd-alex-moi`](https://github.com/ULL-ESIT-SYTW-1617/practica-localstrategy-y-base-de-datos-alex-moi.git#readme) (by Moises Yanes Carballo)—Plugin deploy iaas bbdd
 - [`gitbook-start-iaas-ull-es-alex-moi`](https://github.com/ULL-ESIT-SYTW-1617/gitbook-start-iaas-ull-es-alex-moi.git#readme) (by Moises Yanes Carballo)—Plugin deploy maquina iaas-ull-es
 - [`gitbook-start-iaas-ull-es-merquililycony`](https://github.com/ULL-ESIT-SYTW-1617/gitbook-start-iaas-ull-es-merquililycony#readme) (by Constanza León, Merquis Cruz, Liliana Galiano)—*El objetivo de esta práctica es extender el package NodeJS publicado en npm en una práctica anterior con una nueva* *funcionalidad que permita que los usuarios realizar un despliegue automatico en el servidor de IAAS*
 - [`gitbook-start-plugin-iaas-ull-es-noejaco2017`](http://creacion-de-paquetes-y-modulos-en-nodejs-noejaco2017/README.md) (by alu0100622492)—Despliegue plugin Iaas
 - [`gitc`](https://github.com/cezarlz/gitc#readme) (by Cezar Luiz)—Manage your pull requests and issues from your command line.
 - [`github-publish-npm`](https://github.com/ofersadgat/github-publish-npm) (by Ofer Sadgat)—This will upload publish npm assets to the GitHub Releases API.
 - [`gitlab-ci-variables-cli`](https://github.com/temando/gitlab-ci-variables-cli#readme) (by Khoa Tran)—CLI tool to set/get pipeline variables on Gitlab CI.
 - [`gitline`](https://github.com/cezarlz/gitline#readme) (by Cezar Luiz)—Manage your pull requests and issues from your command line.
 - [`gtni`](https://nmrony.github.io/gtni) (by Nur Mohammed Rony)—Install your all npm dependencies recursively with gtni while you are doing git clone, fetch or pull
 - [`kef-core`](https://npmjs.com/package/kef-core) (by younth)—The awesome KEF
 - [`lcov-server`](https://github.com/gabrielcsapo/lcov-server#readme) (by Gabriel J. Csapo)—🎯 A simple lcov server & cli parser
 - [`moto-connector`](https://npmjs.com/package/moto-connector) (by limingv5)—FEB平台SDK
 - [`nodeschool-admin`](https://github.com/nodeschool/admin#readme) (by Martin Heidegger)—CLI tool for setting up and maintaining a nodeschool chapters and other things.
 - [`ogh`](https://github.com/egoist/ogh#readme) (by EGOIST)—Open GitHub Page of your repo directly in Terminal.
 - [`one-more-gitlab-cli`](https://github.com/chamerling/one-more-gitlab-cli) (by Christophe Hamerling)—One more Gitlab CLI
 - [`pr-log`](https://github.com/lo1tuma/pr-log#readme) (by Mathias Schreck)—Changelog generator based on GitHub Pull Requests
 - [`proyecto-sytw-alex-moi`](https://github.com/ULL-ESIT-SYTW-1617/proyecto-sytw-16-17-alex-moi#readme) (by Moises Yanes Carballo)—Module to build a book on GitBook
 - [`semantic-release`](https://github.com/semantic-release/semantic-release#readme) (by Stephan Bönnemann)—Automated semver compliant package publishing
 - [`ship-release`](https://github.com/IonicaBizau/ship-release#readme)—Publish new versions on GitHub and npm with ease.
 - [`sinit`](https://npmjs.com/package/sinit) (by villadora)—Project initializer based on Scaffold
 - [`smart-clone`](https://github.com/ethernetdan/smart-clone#readme)—Clone a directory into a Golang style directory structure
 - [`ssh-remote`](https://github.com/IonicaBizau/ssh-remote)—Automagically switch on the SSH remote url in a Git repository.
 - [`strapper`](https://npmjs.com/package/strapper) (by Sam Newman)—Coming Soon

## :scroll: License

[MIT][license] © [Ionică Bizău][website]


[badge_patreon]: https://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: https://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: https://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: https://ionicabizau.github.io/badges/paypal_donate.svg

[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2015#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
