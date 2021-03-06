
> An Angular 2 chat app using [Angular 2](https://angular.io/), [RxJS](https://github.com/Reactive-Extensions/RxJS), [Webpack](https://webpack.github.io/), [TypeScript](http://www.typescriptlang.org/), Services, Injectables, [Karma](http://karma-runner.github.io/), Forms, [SCSS](http://sass-lang.com/), and [tslint](http://palantir.github.io/tslint/)

This repo shows an example chat application using RxJS and Angular 2. The goal is to show how to use the Observables data architecture pattern within Angular 2. It also features:

* Webpack configuration with TypeScript, Karma, SCSS, and tslint
* Writing async components that work with RxJS
* How to write injectable services in Angular 2
* And much more


## Quick start

```bash
# clone the repo
git clone https://github.com/ng-book/angular2-rxjs-chat.git 

# change into the repo directory
cd angular2-rxjs-chat

# install 
npm install

# run
npm run go
```

Then visit [http://localhost:8080](http://localhost:8080) in your browser. 

## Architecture

The app has three models:

* [`Message`](app/ts/models.ts#L27) - holds individual chat messages
* [`Thread`](app/ts/models.ts#L12) - holds metadata for a group of `Message`s
* [`User`](app/ts/models.ts#L3) - holds data about an individual user

And there are three services, one for each model:

* [`MessagesService`](app/ts/services/MessagesService.ts) - manages streams of `Message`s
* [`ThreadsService`](app/ts/services/ThreadsService.ts) - manages streams of `Thread`s
* [`UserService`](app/ts/services/UserService.ts) - manages a stream of the current `User`

There are also three top-level components:

* [`ChatNavBar`](app/ts/components/ChatNavBar.ts) - for the top navigation bar and unread messages count
* [`ChatThreads`](app/ts/components/ChatThreads.ts) - for our clickable list of threads 
* [`ChatWindow`](app/ts/components/ChatWindow.ts) - where we hold our current conversation

<div style="clear:both"></div>

## File Structure

Here's an overview of how the files are laid out in this project:

```
angular2-rxjs-chat/
├── Makefile                        * Easy access to common tasks
├── README.md                       * This file
├── app/                            * Where our application code is stored
│   ├── css/                        * Contains our CSS and SCSS files
|   | 
│   ├── images/                     * Stores app images
|   | 
│   ├── index.html                  * HTML entry point
|   | 
│   ├── ts/                         * All of our TypeScript is here
|   |   |
│   │   ├── ChatExampleData.ts      * Contains our bots and sample data
|   |   |
│   │   ├── app.ts                  * App entry point
|   |   |
│   │   ├── components/             * Components go here
|   |   |   |
│   │   │   ├── ChatNavBar.ts       * Nav Bar Component
│   │   │   ├── ChatThreads.ts      * Threads Component
│   │   │   └── ChatWindow.ts       * Chat Window Component
|   |   |
│   │   ├── models.ts               * Our models go here
|   |   |
│   │   ├── services/               * Services here
|   |   |   |
│   │   │   ├── MessagesService.ts  * Manages our messages
│   │   │   ├── ThreadsService.ts   * Exposes our threads
│   │   │   ├── UserService.ts      * Manage our user
│   │   │   └── services.ts         * Exports all services
|   |   |
│   │   └── util/                   * Pipes and various utilities
|   | 
│   ├── typings/                    * Self-managed type definitions here
|   | 
│   └── vendor.js                   * Vendor js requires for webpack
|   | 
├── karma.conf.js                   * Our unit testing configuration
├── package.json                    * Our javascript dependencies
├── test/                           * Our tests go here
├── test.bundle.js                  * Some hacks to get TypeScript tests
├── tsconfig.json                   * Configures the TypeScript compiler
├── tsd.json                        * Configures tsd (type definitions packages)
├── tslint.json                     * Configures our TypeScript linter 
├── typings/                        * tsd managed typings
├── vendor/                         * Various vendored code
└── webpack.config.js               * Our Webpack configuration
```

## Detailed Installation

**Step 1: Install Node.js from the [Node Website](http://nodejs.org/).**

We recommend Node version 4.1 or above. You can check your node version by running this:

```bash
$ node -v
vv4.1...
```

**Step 2: Install Dependencies**

```bash
npm install
```

## Running the App

```bash
npm run go
```

Then visit [http://localhost:8080](http://localhost:8080) in your browser. 

## Running the Tests

You can run the unit tests with:

```bash
npm run test
```

<div style="clear:both"></div>

## License
 [MIT](/LICENSE.md)


