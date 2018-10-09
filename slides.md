# Node.js for Java Developers
<i class="fab fa-twitter"></i>Gangstead

<!-- .element: class="foot" --> JavaMUG 10/10/2018 *slides https://gangstead.github.io/jode-for-nava*
----
- Citations in the notes, press 'S' to enter speaker view and see them.
====
# Outline
- About me
- JS a very brief history
- Node.js even briefer history
- Node.js overview
- Tooling side by side
- When to use and when to avoid Node

====
# Bio
----
![grafikeye](images/grafikeye.jpeg)<!-- .element: class="bio-logo" -->
![c](images/c_lang.jpg)<!-- .element: class="fragment bio-logo" data-fragment-index="1" -->
![java](images/java_logo.jpg)<!-- .element: class="fragment bio-logo" data-fragment-index="2" -->
![scala](images/scala_logo.jpeg)<!-- .element: class="fragment bio-logo" data-fragment-index="3" -->
![node](images/node_logo.jpg)<!-- .element: class="fragment bio-logo" data-fragment-index="4" -->
----
## ![](images/nodeschool-dallas-skyline.png)<!-- .element class="heading-logo" --> Code's Cool Dallas

- Hands-on coding workshops
- <!-- .element: class="fragment" data-fragment-index="1" --> Formerly Nodeschool Dallas, now Node & more
- <!-- .element: class="fragment" data-fragment-index="2" --> Started Jan 2015, 40 past events
- <!-- .element: class="fragment" data-fragment-index="3" --> [meetup.com/CodesCool-Dallas](https://www.meetup.com/CodesCool-Dallas/)

====
# JS History
----
JavaScript, like Java, right?
----
### Netscape _Mocha_<!-- .element: class="highlight" --> project
- Brendan Eich at Netscape wanted to bring _Scheme_<!-- .element: class="highlight" --> and _Self_<!-- .element: class="highlight" --> to the startup Netscape
- Netscape teamed up with Sun Microsystems to bring their *interactive TV language* to the browser
- He built _Mocha_ in May 1995. It was released in September 1995 as _LiveScript_
  - <!-- .element: class="fragment foot highlight" data-fragment-index="1" --> I mean started and finished in 10 days in May 1995
  - <!-- .element: class="fragment foot highlight" data-fragment-index="1" --> Java project started in June 1991, Java 1.0 released January 1996.
Note: Marc Andreessen, of a17z wanted a "glue language" for the browser that was easy to use and could be embedded directly in the markup.  That's why the talks with Sun pivoted from Java in the browser back to a scripting language that could "complement" Java. So Eich's planned language was given a Java-like syntax.
----
<!-- .element: class="text-left" -->
- Some excerpts about _Scheme_<!-- .element: class="highlight" -->

> …a programming language that supports multiple paradigms, including functional programming and imperative programming,[1] and is one of the two main dialects of Lisp. Unlike Common Lisp, the other main dialect, Scheme follows a minimalist design philosophy specifying a small standard core with powerful tools for language extension…<!-- .element: class="foot" -->

- And _Self_<!-- .element: class="highlight" -->

> … an object-oriented programming language based on the concept of prototypes. Self began as a dialect of Smalltalk, being dynamically typed and using just-in-time compilation (JIT) …<!-- .element: class="foot" -->
----
## So why team up with ![](images/sun_logo.png)<!-- .element class="heading-logo" -->?
- In one year of being released Netscape had about 75% share of browser market
- Microsoft said "that's a nice market you have there, it'd be a shame if something were to happen to it"
Note: Netscape wanted JS to be the companion language to Java like Visual Basic was to C++

----
## Standardization
- August 1996 - Microsoft included a reverse engineered `JScript` in Internet Explorer 3
- November 1996 - Netscape submits JavaScript standard to ECMA International
  - All browsers can now implement the same language, which they promptly do.  The end.
----
## JS engines
- SpiderMonkey - Netscape and now FireFox. Written by Brendon Eich. Maintained by Mozilla C/C++
- Rhino - developed by original Netscape team in Java for Java. Compiled & Interpreted mode.  Maintained by Mozilla
- Nashorn - replacement for Rhino Java ≥ 1.8
- Chakra - engine for IE 9 + and Edge. C++
Note: IE < 9 had a JS interpreter JScript but Chakra compiles to machine code like all the other engines.
----
## JS engines
- ![](images/squirrelfish_logo.svg)<!-- .element style="height:2em" --> ![](images/webkit_logo.png)<!-- .element style="height:2em" --> JavaScriptCore/SquirelFish - webkit's JS engine, from KDE project. C++
- ![](images/v8_logo.png)<!-- .element style="height:2em" -->V8 .  For Chrome browser but intended to be used as a stand alone project. Since 2017 Node is one of the targets of V8 and included in tests. *Don't Break Node* C++

----
## JS continues to evolve
- coercion in == ⟶ === ES3
- no block scope ⟶ `let` and `const` ES2015
- no classes, just prototypes ⟶ classes ES2015 (syntactic sugar)
- Callback hell ⟶ promises ES2015
- no modules ⟶ (require in Node) modules in ES2015
- exponential operator ES2016
- Rest and Spread operators in object assignments (not just arrays and arguments) ES2018
- I want pipes like F# & Erlang ⟶ `|>` [TC39 proposal](https://github.com/tc39/proposal-pipeline-operator)
====
# Node.js history
----
- 1996 ![](images/netscape_enterprise_server.gif)
- LiveWire component of NES was a compiled JS environment used to access DB resources kind of like PHP in special tags in the html files
- Also 1996 IIS jscript for ASP and .NET pages
Note: http://philip.greenspun.com/wtr/livewire.html
----
- Mid 2000's
- September 2008 Google releases Chrome browser with JS engine V8 that has greater performance than all other browsers
----
![](images/joyent_logo.png)<!-- .element style="height:3em"-->
- Ryan Dahl, employee at software & services firm Joyent makes first Node commits
- Combine Chrome's V8 js engine with an event loop and some IO libraries (http, file, etc)
- First release May 2009.
- September 2009 Isaac Schlueter proposes npm…
----
<!-- .slide: data-background-image="images/npm_package_delivery.png" data-background-size="contain"-->
----
- 2012 Ryan Dahl steps away from Node
- 2015 IO.js fork and spoon lead to formation of Node Foundation
- Joyent's bumbling stewardship comes to an end
![](images/nodejs_foundation_logo.png)<!-- .element style="height:3em"-->
----
![](images/ts_logo.png)<!-- .element style="height:3em"-->
- 2016 Typescript 2.0 and Visual Studio Code GA released
- Both are Microsoft projects had been around for years but this was when they were really ready for wide adoption
----
#### Node.js is JavaScript
and npm is the package manager for the web (3 Billion downloads/week)
- npm used for front and back end dependencies
- 10/4/18 Node + JS Foundations announce [intent to merge](https://blog.npmjs.org/post/178734613655/node-js-foundation)
Note: https://flaviocopes.com/node-history/  JS Foundation formerly called J Query Foundation and houses tons of JS projects like Grunt, JerryScript, ESLint, Lodash, Mocha, Moment, Webpack.
====
# Node.js overview
----
- V8
- Single threaded event loop
- IO libraries
- package manager
- <!-- .element: class="fragment" data-fragment-index="1" -->![](images/duct-tape.jpeg)
----
<!-- .slide: data-background-image="images/nodejs-event-loop.png" data-background-color="white" data-background-size="contain"-->
But hey it's supposed to be single threaded<!-- .element: class="blocking-text fragment" data-fragment-index="1" -->
----
<!-- .slide: data-background-image="images/Event_Loop_in_Node.js.png" data-background-color="white" data-background-size="contain"-->
----
<!-- .element class="strong-contrast" -->
- Assertion Testing, Async Hooks, Buffer, C++ Addons, C/C++ Addons - N-API, Child Processes
- Cluster, Command Line Options, **Console**, Crypto, Debugger, Deprecated APIs, **DNS**, **Domain**, ECMAScript Modules, Errors, Events
- **File System**, Globals, **HTTP**, **HTTP/2**, **HTTPS**, Inspector, Internationalization, Modules, Net
- OS, **Path**, Performance Hooks, **Process**, Punycode, **Query Strings**, **Readline**, REPL, **Stream**
- String Decoder, Timers, **TLS/SSL**, Tracing, **TTY**, **UDP/Datagram**, **URL**, Utilities, V8, VM, ZLIB
Note: https://nodejs.org/dist/latest-v8.x/docs/api/
----
### npm
- command line tool
- also the registry of packages
  - free public packages
    - top level and namespaced
  - paid private
    - private packages or self hosted
  - alternative CLIs use same registry (yarn)
- private company, but distributed with node
Note: it's kind of weird since Node.js is run by the foundation but npm, inc is for-profit
----
<!-- .element class="inline-code-contrast" -->
# Duct tape
- All your regular JS [built in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) plus `modules`, `exports`, `require`, `console`, [and more](https://nodejs.org/api/globals.html)
- REPL
- inspector (Chrome developer tools for Node.js)
====
# Tooling side by side
----
## starting a program
```
> javac worldstar.java
> java worldstar.class
> node worldstar.js
```
----
## environment variables
```java
System.getenv("FOO");
```
```js
process.env.FOO;  process.env['FOO'];
```
----
## Command line arguments
```java
public static void main(String[] args) {
  System.out.println(args);
}
```
```js
console.log(process.argv);
```
----
## Import vs require
```java
  // in src/main/java/org/springframework/samples/mvc/convert/JavaBean.java
  import java.util.Date;
  import java.util.List;
  import java.util.Map;
  import org.springframework.format.annotation.DateTimeFormat;
```
```js
  // in lib/utils/convert.js
  const moment = require('moment');
  import { flatMap, max, has } from 'lodash'; //es modules
```

Note: Not making this file name up: https://github.com/spring-projects/spring-mvc-showcase/blob/master/src/main/java/org/springframework/samples/mvc/convert/JavaBean.java
----
npm vs maven

- package.json vs pom.xml
- JS community much better about semver

```xml
<dependency>
  <groupId>org.glassfish</groupId>
  <artifactId>javax.el</artifactId>
  <version>3.0.1-b08</version>
</dependency>
```
<!-- .element class="left-col" -->

```json
  "express": "^4.16.2",
```
<!-- .element class="right-col" -->

----
npm vs maven build steps
- Maven has some magic spring boot module builds
- Built in list of lifecycle phases: `validate`, `compile`, `test`, `package`, `verify`, `install`, `deploy` and others depending on package value.
```json
  "scripts": {
    "build": "grunt default",
    "deluxe-build": "complicatedBuild.sh",
    "test": "mocha .",
    "posttest": "coveralls",
    "test-special": "mocha --opts test/special/mocha.opts"
  }
```

<!-- .element: class="foot" --> Define your own.  Bash scripts that are executed with your node path set up. Only special hooks is for script `X` `preX` and `postX` will be run automatically
----
<!-- .element class="inline-code-contrast" -->

# Dependencies

- Maven
- `~/.m2`
- Version names roughly meaningless
- Resolves exact version
- Stores all specified versions
- Dependencies are few and large

<!-- .element class="left-col" -->

- npm
- `/node_modules` _most common_<!-- .element class="foot" -->
- `~/node_modules` _global, usually CLI tools_ <!-- .element class="foot" -->
- Community fairly good at [semver](https://semver.org/)
  - Any text is considered a "prerelease tag"
- Can specify [ranges](https://docs.npmjs.com/misc/semver)
  - <!-- .element class="foot" -->`^3.2.1` (most common), `~1.2.3`, `>4`, `2.*`
- Enough versions to resolve every dependency
- Numerous and small

<!-- .element class="right-col" -->
----
<!-- .slide: data-background-image="images/maven_support.jpg" data-background-size="contain"-->
----
SpringMVC vs express/hapi/some framework I read about in a blog post
- [Spring MVC PetClinic CRUD routes](https://github.com/spring-projects/spring-petclinic/blob/38bd3280cbb765c5e3045f646f9c09523d0ba051/src/main/java/org/springframework/samples/petclinic/owner/OwnerController.java#L61)
- [Example Express CRUD routes](https://github.com/gothinkster/node-express-realworld-example-app/blob/master/routes/api/users.js#L63)
- [Example Hapi CRUD routes](https://github.com/gangstead/keepalive-service/blob/master/routes/users.js#L21)

Note: TODO: find spring example that's not MVC.  Spring is annotations galore

----
#### Remember how _Scheme_<!-- .element: class="highlight" --> had a 'small standard core'?
----
<!-- .slide: data-background-image="images/meme_js_framework.jpg" data-background-color="white" data-background-size="contain"-->
----
### Database with ORM, set up connection
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<persistence xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_2_0.xsd"
    version="2.0" xmlns="http://java.sun.com/xml/ns/persistence">
    <persistence-unit name="todos" transaction-type="RESOURCE_LOCAL">
        <class>de.vogella.jpa.simple.model.Todo</class>
 <properties>
  <property name="javax.persistence.jdbc.driver" value="org.apache.derby.jdbc.EmbeddedDriver" />
  <property name="javax.persistence.jdbc.url"
    value="jdbc:derby:/home/vogella/databases/simpleDb;create=true" />
  <property name="javax.persistence.jdbc.user" value="test" />
  <property name="javax.persistence.jdbc.password" value="test" />

  <!-- EclipseLink should create the database schema automatically -->
  <property name="eclipselink.ddl-generation" value="create-tables" />
  <property name="eclipselink.ddl-generation.output-mode" value="database" />
 </properties>

    </persistence-unit>
</persistence>
```
<!-- .element class="left-col tall-code" -->

```js
const Sequelize = require('sequelize');
const sequelize = new Sequelize('database',
  proces.env.DB_USER,
  process.env.DB_PASS,
  {
    host: process.env.DB_HOST,
    dialect: 'postgres',

    pool: {
      max: 5,
      min: 2
    }
  });
```
<!-- .element class="right-col tall-code" -->
Note:
- [JS ORM Comparison](https://medium.freecodecamp.org/a-comparison-of-the-top-orms-for-2018-19c4feeaa5f) but even it says to just use joi and knex
- How do you manage the JPA secret values in production? I'm not sure what the equivalent
----
### Database with ORM, define the model
```java
// this could also be done withi a lot of xml
// package and import statements
@Entity
@Table(name="user")
public class User {
  @Id
  @Column(name="username")
  private String username;
  @Column(name="birthday")
  private Date birthday;

  public String getUsername() {
    return username;
  }
  public void setUsername(String username) {
    this.username = username;
  }
  public Date getBirthday() {
    return birthday;
  }
  public void setBirthday(Date birthday) {
    this.birthday = birthday;
  }
  // and a toString if you want any useful debugging...
}
```
<!-- .element class="left-col tall-code" -->

```js
const User = sequelize.define('user', {
  username: {
    type: Sequelize.STRING
    primaryKey: true
  },
  birthday: Sequelize.DATE
});
```
<!-- .element class="right-col tall-code" -->

----
### Database with ORM, make a query

All of this is to avoid writing some simple sql statements <!-- .element class="foot fragment" data-fragment-index="1" -->

```java
  EntityManagerFactory emfactory = Persistence.
    createEntityManagerFactory( "user" );
  EntityManager entitymanager = emfactory.
    createEntityManager( );
  entitymanager.getTransaction( ).begin( );

  //create
  User user = new User();
  user.setUsername("Gangstead");
  user.setBirthday(new Date())
  entitymanager.persist( user );
  entitymanager.getTransaction( ).commit( );
  entitymanager.close( );

  //find
  User user=entitymanager.
          find( User.class, "Gangstead" );

  emfactory.close( );

```
<!-- .element class="left-col tall-code" -->

```js
//create
await User.create({
  username: 'Gangstead',
  birthday: new Date()
});

//find
const u = await User.findOne({
  where: {
    name: {
      [Op.iLike]: 'gangstead'
    }
  }
});
```
<!-- .element class="right-col tall-code" -->

----
### Database without ORM

knex code is very close to SQL, easily drops into sql when needed

```js
// Migration file that sets up the table
exports.up = (knex) => {
  return knex.schema.raw('CREATE EXTENSION IF NOT EXISTS "uuid-ossp"')
    .then(() => knex.schema.createTable('users', (t) => {
      t.uuid('id').primary().defaultTo(knex.raw('uuid_generate_v4()'));
      t.string('username').notNullable();
      t.date('birthday').notNullable();
    }));
};

// Create
await knex('users').insert({
  username: req.body.username,
  birithday: req.body.birthday
})

// Find
const p = knex('users')
      .first('*')
      .where('username', req.params.username)
      .then((u) => ({ user: formatUser(u) }));
```
<!-- .element class="tall-code" -->

Note: [source](https://github.com/gangstead/keepalive-service/blob/master/routes/buttons.js#L89)
 - TypeORM supposed to be like Hibernate
----
# NoSQL ORM
- Mongoose Technically for MongoDb but I use it with Kosmos DB on Azure
```js
var kittySchema = new mongoose.Schema({
  name: String
});
var Kitten = mongoose.model('Kitten', kittySchema);
var fluffy = new Kitten({ name: 'fluffy' });
fluffy.save().then(() => Kitten.find({ name: /^fluff/ }))
.then((cat) => console.log(`Found cat: ${cat.name}`));
```
----
![](images/onemorething.png)

<!-- .element class="foot fragment" data-fragment-index="1" -->…there's types
----
# TypeScript
- Superset of ES2015 (aka ES6) which is a superset of ES5 (aka JavaScript)
- TypeScript "compiler" transpiles to JavaScript
- Zero performance hit, types are gone at run time
- VS Code support is really good, blurs the line between text editor and IDE*
- Gives you the warm fuzzies of types*

<!-- .element class="foot fragment" data-fragment-index="1" -->* usually considered a good thing
----
```typescript
  //typescript
  export const enum Sex {
    Unspecified = 0,
    Female = 1,
    Male = 2,
    Other = 3,
    Unknown = 4
  }
  private messageSexMap(s: Sex): string {
      switch(s) {
          case Sex.Unspecified:
              return 'U';
          case Sex.Female:
              return 'F';
          case Sex.Male:
              return 'M';
          case Sex.Other:
              return 'O';
          case Sex.Unknown:
              return 'U';
      }
  }
```
<!-- .element class="left-col tall-code" -->

```js
    //js
    MessageExportRoutes.prototype.messageSexMap = function (s) {
        switch (s) {
            case 0:
                return 'U';
            case 1:
                return 'F';
            case 2:
                return 'M';
            case 3:
                return 'O';
            case 4:
                return 'U';
        }
    };
```
<!-- .element class="right-col tall-code" -->
----
![](images/jstscheckmorpheus.jpg)
====
# When to/not to use Node
----
# When to Node
----
#### Node's first README

```markdown
WHEREAS, The usage of threads has complicated computer programming; and

WHEREAS, V8 javascript comes free of I/O and threads; and

WHEREAS, Most operating systems do not provide asynchonous file system
access.

Now, therefore:

This set server and client libraries were made to build simple but fast
servers. They are provided free of charge under a permissive simple license.

Submitted by
Ryah Dahl, Programmer
Tim Becker, Programmer
March 1, 2009
```
<!-- .element class="tall-code" -->

Note: https://github.com/nodejs/node-v0.x-archive/tree/1afe6d26dbcf76de15df7e2c8fc3aadbbb8b117d
----
### For the web
- IO heavy
- Data streaming
- REST API
- Numerous connections
- Your problem scales out well
- <!-- .element: class="fragment" data-fragment-index="1" -->JDK11 Licenses got you down
----
<!-- .slide: data-background-image="images/meme_oracle_license.jpg" data-background-color="white" data-background-size="contain"-->
----
### Functions As a Service
λ
- Performance wise Node and Java are similar
- Node.js is going to be much easier to develop
  - Example on serverless framework [30 lines of node](https://github.com/serverless/examples/tree/master/aws-node-dynamodb-backup) vs [hundreds of lines of java](https://github.com/igorbakman/java-lambda-dynamodb)
- Lots more activity in Node than in Java
- λ functions start out at 128 MB of ram
----
### Docker
- Base image size: [node:8-alpine 22mb](https://hub.docker.com/r/library/node/tags/) vs [java:8-alpine 52mb](https://hub.docker.com/r/library/java/tags/)
- JVM Takes too many resources and Java 8 will see kubernetes' memory and think it's all for one container [*](https://medium.com/metrosystemsro/why-i-would-not-choose-java-to-run-in-kubernetes-be73de7294e7)
  - Remember: a container is not a VM!
  - Buggy behavior and bad defaults for Java 8, Java 10 is better [*](https://developers.redhat.com/blog/2017/03/14/java-inside-docker/)
  - Needs careful tuning [*](https://codefresh.io/docker-tutorial/java_docker_pipeline/)
- <!-- .element class="fragment" data-fragment-index="1" -->Node
  - Single threaded: throwing more RAM at node isn't really necessary
  - Scale horizontally: Easy to start up another container
  - Evolved at same time: more things set with command line flags & environment variables

----
## Because this guy said so
- [Why is a Java guy so excited about Node.js?](https://blog.sourcerer.io/why-is-a-java-guy-so-excited-about-node-js-and-javascript-7cfc423efb44)
- 10+ Year Java SE team member at Sun
- TL;DR of the Tl;DR - Both have good performance but "Coding with Node.js is a joy"
----
# When not to Node
----
## Computation bound
- Long math calculations
- Your problem scales up
- When number precision matters.  Javascript only has one number type: double precision 64 bit floats.
Note: Node is single threaded.  If you need to multiply some huge matrices you will be stuck in one thread
----
<!-- .slide: data-background-image="images/jsgoodparts.jpeg" data-background-size="contain"-->
Note: Trivia: the Rhino js engine was named after the Rhino on that book, which came out the year the Netscape team was developing Rhino
====
# The end
#### Tl;DR Use VS Code + TypeScript and you'll be fine
@Gangstead
