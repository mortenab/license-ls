# License List
List licenses for installed packages.  

![npm](https://img.shields.io/npm/v/license-ls.svg)
[![Maintainability](https://api.codeclimate.com/v1/badges/dbc11e7aa9d037034303/maintainability)](https://codeclimate.com/github/morficus/license-ls/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/dbc11e7aa9d037034303/test_coverage)](https://codeclimate.com/github/morficus/license-ls/test_coverage)
[![Build Status](https://travis-ci.org/morficus/license-ls.svg?branch=master)](https://travis-ci.org/morficus/license-ls)

## Features
* JSON, CSV, XML or ASCII table output
* Specify the package depth
* Ability to limit list to only dev or only production packages
* Support for converting SPDX expressions in to their full names
* Specify what properties should be included in the out
* Can be used programmatically for maximum flex- and extensibility

## Options
You can always run `npx license-ls --help` to get this documentation

* `--help`: show help
* `--format`: output format. json, table, xml or csv (defaults to table)
* `--include`: List of properties to include
* `--depth`:  Max display depth of the dependency tree
* `--production, --prod`:   Display only the dependency tree for packages in dependencies
* `--development, --dev`:  Display only the dependency tree for packages in devDependencies
* `--global`:  List packages in the global install prefix instead of in the current project
* `--link`:  Display only dependencies which are linked 

### CSV specific options 
* `--csv.delimiter`: character the use as the value separator (defaults to `,`)

### Table specific options
* `--table.header.*`: changes the default header name for table output (ie: `--header.name=Module`)
  * Here is a list of possible values for `*`: `id`, `name`, `version`, `license`, `homepage`, `repository`, `author`, `dependencyLevel`

### XML specific options
* `--xml.asAttrs`: uses each package property as the XML tag element, with the package name as the content (see "XML Output #2" in the Examples section) 

## Examples
Get a list of all dependency packages
```bash
npx license-ls
```

Get a list of only direct dependencies
```bash
npx license-ls --depth=0
```

Get a list of only direct production dependencies
```bash
npx license-ls --depth=0 --prod
```

Get a list of only direct production dependencies, only show directory path, name and license
```bash
npx license-ls --depth=0 --prod --include=path,name,license
```

Get a list of all dependency packages in JSON format
```bash
npx license-ls --format=json
```

Save results to a file
```bash
npx license-ls --depth=0 > report.txt
```

Set some custom table headers
```bash
npx license-ls --depth=0 --table.header.name=Module --table.header.repository="Repo URL" --table.header.author="Who made this?"
```

## Sample Output formats
All of the following samples were generated by running the relevant command against this project.   

### JSON output
```npx license-ls --format=json --depth=0```
```json
 [
   {
     "id": 0,
     "name": "ava",
     "version": "2.1.0",
     "license": "MIT License (MIT)",
     "repository": "git+https://github.com/avajs/ava.git",
     "homepage": "https://avajs.dev",
     "path": "/Users/morficus/workspace/license-ls/node_modules/ava",
     "dependencyLevel": "development"
   },
   {
     "id": 1,
     "name": "debug",
     "version": "4.1.1",
     "license": "MIT License (MIT)",
     "repository": "git://github.com/visionmedia/debug.git",
     "author": "TJ Holowaychuk",
     "homepage": "https://github.com/visionmedia/debug#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/debug",
     "dependencyLevel": "development"
   },
   {
     "id": 2,
     "name": "json2csv",
     "version": "4.5.1",
     "license": "MIT License (MIT)",
     "repository": "git+https://github.com/zemirco/json2csv.git",
     "author": "Mirco Zeiss",
     "homepage": "https://github.com/zemirco/json2csv#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/json2csv",
     "dependencyLevel": "production"
   },
   {
     "id": 3,
     "name": "jstoxml",
     "version": "1.5.0",
     "license": "MIT License (MIT)",
     "repository": "git://github.com/davidcalhoun/jstoxml.git",
     "author": "David Calhoun",
     "homepage": "http://github.com/davidcalhoun/jstoxml",
     "path": "/Users/morficus/workspace/license-ls/node_modules/jstoxml",
     "dependencyLevel": "production"
   },
   {
     "id": 4,
     "name": "libnpm",
     "version": "2.0.1",
     "license": "ISC License (ISC)",
     "repository": "git+https://github.com/npm/libnpm.git",
     "author": "Kat Marchán",
     "homepage": "https://github.com/npm/libnpm#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/libnpm",
     "dependencyLevel": "production"
   },
   {
     "id": 5,
     "name": "nyc",
     "version": "14.1.1",
     "license": "ISC License (ISC)",
     "repository": "git+ssh://git@github.com/istanbuljs/nyc.git",
     "author": "Ben Coe",
     "homepage": "https://github.com/istanbuljs/nyc#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/nyc",
     "dependencyLevel": "production"
   },
   {
     "id": 6,
     "name": "ora",
     "version": "3.4.0",
     "license": "MIT License (MIT)",
     "repository": "git+https://github.com/sindresorhus/ora.git",
     "author": "Sindre Sorhus",
     "homepage": "https://github.com/sindresorhus/ora#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/ora",
     "dependencyLevel": "production"
   },
   {
     "id": 7,
     "name": "read-package-tree",
     "version": "5.2.2",
     "license": "ISC License (ISC)",
     "repository": "git+https://github.com/npm/read-package-tree.git",
     "author": "Isaac Z. Schlueter",
     "homepage": "https://github.com/npm/read-package-tree",
     "path": "/Users/morficus/workspace/license-ls/node_modules/read-package-tree",
     "dependencyLevel": "production"
   },
   {
     "id": 8,
     "name": "spdx-expression-parse",
     "version": "3.0.0",
     "license": "MIT License (MIT)",
     "repository": "git+https://github.com/jslicense/spdx-expression-parse.js.git",
     "author": "Kyle E. Mitchell",
     "homepage": "https://github.com/jslicense/spdx-expression-parse.js#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/spdx-expression-parse",
     "dependencyLevel": "production"
   },
   {
     "id": 9,
     "name": "spdx-license-list",
     "version": "6.0.0",
     "license": "Creative Commons Zero v1.0 Universal (CC0-1.0)",
     "repository": "git+https://github.com/sindresorhus/spdx-license-list.git",
     "author": "Sindre Sorhus",
     "homepage": "https://github.com/sindresorhus/spdx-license-list#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/spdx-license-list",
     "dependencyLevel": "production"
   },
   {
     "id": 10,
     "name": "table",
     "version": "5.4.1",
     "license": "BSD 3-Clause \"New\" or \"Revised\" License (BSD-3-Clause)",
     "repository": "git+https://github.com/gajus/table.git",
     "author": "Gajus Kuizinas",
     "homepage": "https://github.com/gajus/table#readme",
     "path": "/Users/morficus/workspace/license-ls/node_modules/table",
     "dependencyLevel": "production"
   },
   {
     "id": 11,
     "name": "yargs",
     "version": "13.2.4",
     "license": "MIT License (MIT)",
     "repository": "git+https://github.com/yargs/yargs.git",
     "homepage": "https://yargs.js.org/",
     "path": "/Users/morficus/workspace/license-ls/node_modules/yargs",
     "dependencyLevel": "production"
   }
 ]
```

### CSV output
```npx license-ls --format=csv --depth=0```
```csv
"id","name","version","license","repository","author","homepage","path","dependencyLevel"
0,"ava","2.1.0","MIT License (MIT)","git+https://github.com/avajs/ava.git",,"https://avajs.dev","/Users/morficus/workspace/license-ls/node_modules/ava","development"
1,"debug","4.1.1","MIT License (MIT)","git://github.com/visionmedia/debug.git","TJ Holowaychuk","https://github.com/visionmedia/debug#readme","/Users/morficus/workspace/license-ls/node_modules/debug","development"
2,"json2csv","4.5.1","MIT License (MIT)","git+https://github.com/zemirco/json2csv.git","Mirco Zeiss","https://github.com/zemirco/json2csv#readme","/Users/morficus/workspace/license-ls/node_modules/json2csv","production"
3,"jstoxml","1.5.0","MIT License (MIT)","git://github.com/davidcalhoun/jstoxml.git","David Calhoun","http://github.com/davidcalhoun/jstoxml","/Users/morficus/workspace/license-ls/node_modules/jstoxml","production"
4,"libnpm","2.0.1","ISC License (ISC)","git+https://github.com/npm/libnpm.git","Kat Marchán","https://github.com/npm/libnpm#readme","/Users/morficus/workspace/license-ls/node_modules/libnpm","production"
5,"nyc","14.1.1","ISC License (ISC)","git+ssh://git@github.com/istanbuljs/nyc.git","Ben Coe","https://github.com/istanbuljs/nyc#readme","/Users/morficus/workspace/license-ls/node_modules/nyc","production"
6,"ora","3.4.0","MIT License (MIT)","git+https://github.com/sindresorhus/ora.git","Sindre Sorhus","https://github.com/sindresorhus/ora#readme","/Users/morficus/workspace/license-ls/node_modules/ora","production"
7,"read-package-tree","5.2.2","ISC License (ISC)","git+https://github.com/npm/read-package-tree.git","Isaac Z. Schlueter","https://github.com/npm/read-package-tree","/Users/morficus/workspace/license-ls/node_modules/read-package-tree","production"
8,"spdx-expression-parse","3.0.0","MIT License (MIT)","git+https://github.com/jslicense/spdx-expression-parse.js.git","Kyle E. Mitchell","https://github.com/jslicense/spdx-expression-parse.js#readme","/Users/morficus/workspace/license-ls/node_modules/spdx-expression-parse","production"
9,"spdx-license-list","6.0.0","Creative Commons Zero v1.0 Universal (CC0-1.0)","git+https://github.com/sindresorhus/spdx-license-list.git","Sindre Sorhus","https://github.com/sindresorhus/spdx-license-list#readme","/Users/morficus/workspace/license-ls/node_modules/spdx-license-list","production"
10,"table","5.4.1","BSD 3-Clause ""New"" or ""Revised"" License (BSD-3-Clause)","git+https://github.com/gajus/table.git","Gajus Kuizinas","https://github.com/gajus/table#readme","/Users/morficus/workspace/license-ls/node_modules/table","production"
11,"yargs","13.2.4","MIT License (MIT)","git+https://github.com/yargs/yargs.git",,"https://yargs.js.org/","/Users/morficus/workspace/license-ls/node_modules/yargs","production"
```



### Table output
```npx license-ls --depth=0```
```text
╔═══════╤═══════════════════════╤═════════╤════════════════════════════════════════════════════════╤═══════════════════════════════════════════════════════════════╤════════════════════╤══════════════════════════════════════════════════════════════╤════════════════════════════════════════════════════════════════════════════════╤═════════════════╗
║ Row # │ Package Name          │ Version │ License                                                │ Repository                                                    │ Author             │ Homepage                                                     │                                                                                │ Dependency type ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 0     │ ava                   │ 2.1.0   │ MIT License (MIT)                                      │ git+https://github.com/avajs/ava.git                          │                    │ https://avajs.dev                                            │ /Users/morficus/workspace/license-ls/node_modules/ava                   │ development     ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 1     │ debug                 │ 4.1.1   │ MIT License (MIT)                                      │ git://github.com/visionmedia/debug.git                        │ TJ Holowaychuk     │ https://github.com/visionmedia/debug#readme                  │ /Users/morficus/workspace/license-ls/node_modules/debug                 │ development     ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 2     │ json2csv              │ 4.5.1   │ MIT License (MIT)                                      │ git+https://github.com/zemirco/json2csv.git                   │ Mirco Zeiss        │ https://github.com/zemirco/json2csv#readme                   │ /Users/morficus/workspace/license-ls/node_modules/json2csv              │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 3     │ jstoxml               │ 1.5.0   │ MIT License (MIT)                                      │ git://github.com/davidcalhoun/jstoxml.git                     │ David Calhoun      │ http://github.com/davidcalhoun/jstoxml                       │ /Users/morficus/workspace/license-ls/node_modules/jstoxml               │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 4     │ libnpm                │ 2.0.1   │ ISC License (ISC)                                      │ git+https://github.com/npm/libnpm.git                         │ Kat Marchán        │ https://github.com/npm/libnpm#readme                         │ /Users/morficus/workspace/license-ls/node_modules/libnpm                │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 5     │ nyc                   │ 14.1.1  │ ISC License (ISC)                                      │ git+ssh://git@github.com/istanbuljs/nyc.git                   │ Ben Coe            │ https://github.com/istanbuljs/nyc#readme                     │ /Users/morficus/workspace/license-ls/node_modules/nyc                   │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 6     │ ora                   │ 3.4.0   │ MIT License (MIT)                                      │ git+https://github.com/sindresorhus/ora.git                   │ Sindre Sorhus      │ https://github.com/sindresorhus/ora#readme                   │ /Users/morficus/workspace/license-ls/node_modules/ora                   │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 7     │ read-package-tree     │ 5.2.2   │ ISC License (ISC)                                      │ git+https://github.com/npm/read-package-tree.git              │ Isaac Z. Schlueter │ https://github.com/npm/read-package-tree                     │ /Users/morficus/workspace/license-ls/node_modules/read-package-tree     │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 8     │ spdx-expression-parse │ 3.0.0   │ MIT License (MIT)                                      │ git+https://github.com/jslicense/spdx-expression-parse.js.git │ Kyle E. Mitchell   │ https://github.com/jslicense/spdx-expression-parse.js#readme │ /Users/morficus/workspace/license-ls/node_modules/spdx-expression-parse │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 9     │ spdx-license-list     │ 6.0.0   │ Creative Commons Zero v1.0 Universal (CC0-1.0)         │ git+https://github.com/sindresorhus/spdx-license-list.git     │ Sindre Sorhus      │ https://github.com/sindresorhus/spdx-license-list#readme     │ /Users/morficus/workspace/license-ls/node_modules/spdx-license-list     │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 10    │ table                 │ 5.4.1   │ BSD 3-Clause "New" or "Revised" License (BSD-3-Clause) │ git+https://github.com/gajus/table.git                        │ Gajus Kuizinas     │ https://github.com/gajus/table#readme                        │ /Users/morficus/workspace/license-ls/node_modules/table                 │ production      ║
╟───────┼───────────────────────┼─────────┼────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────┼────────────────────┼──────────────────────────────────────────────────────────────┼────────────────────────────────────────────────────────────────────────────────┼─────────────────╢
║ 11    │ yargs                 │ 13.2.4  │ MIT License (MIT)                                      │ git+https://github.com/yargs/yargs.git                        │                    │ https://yargs.js.org/                                        │ /Users/morficus/workspace/license-ls/node_modules/yargs                 │ production      ║
╚═══════╧═══════════════════════╧═════════╧════════════════════════════════════════════════════════╧═══════════════════════════════════════════════════════════════╧════════════════════╧══════════════════════════════════════════════════════════════╧════════════════════════════════════════════════════════════════════════════════╧═════════════════╝
```

### XML Output #1
```npx license-ls --depth=0 --format=xml```
```xml
<dependencies>
    <dependency>
        <id>0</id>
        <name>ava</name>
        <version>2.1.0</version>
        <license>MIT License (MIT)</license>
        <repository>git+https://github.com/avajs/ava.git</repository>
        <author/>
        <homepage>https://avajs.dev</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/ava</path>
        <dependencyLevel>development</dependencyLevel>
    </dependency>
    <dependency>
        <id>1</id>
        <name>debug</name>
        <version>4.1.1</version>
        <license>MIT License (MIT)</license>
        <repository>git://github.com/visionmedia/debug.git</repository>
        <author>TJ Holowaychuk</author>
        <homepage>https://github.com/visionmedia/debug#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/debug</path>
        <dependencyLevel>development</dependencyLevel>
    </dependency>
    <dependency>
        <id>2</id>
        <name>json2csv</name>
        <version>4.5.1</version>
        <license>MIT License (MIT)</license>
        <repository>git+https://github.com/zemirco/json2csv.git</repository>
        <author>Mirco Zeiss</author>
        <homepage>https://github.com/zemirco/json2csv#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/json2csv</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>3</id>
        <name>jstoxml</name>
        <version>1.5.0</version>
        <license>MIT License (MIT)</license>
        <repository>git://github.com/davidcalhoun/jstoxml.git</repository>
        <author>David Calhoun</author>
        <homepage>http://github.com/davidcalhoun/jstoxml</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/jstoxml</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>4</id>
        <name>libnpm</name>
        <version>2.0.1</version>
        <license>ISC License (ISC)</license>
        <repository>git+https://github.com/npm/libnpm.git</repository>
        <author>Kat Marchán</author>
        <homepage>https://github.com/npm/libnpm#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/libnpm</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>5</id>
        <name>nyc</name>
        <version>14.1.1</version>
        <license>ISC License (ISC)</license>
        <repository>git+ssh://git@github.com/istanbuljs/nyc.git</repository>
        <author>Ben Coe</author>
        <homepage>https://github.com/istanbuljs/nyc#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/nyc</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>6</id>
        <name>ora</name>
        <version>3.4.0</version>
        <license>MIT License (MIT)</license>
        <repository>git+https://github.com/sindresorhus/ora.git</repository>
        <author>Sindre Sorhus</author>
        <homepage>https://github.com/sindresorhus/ora#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/ora</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>7</id>
        <name>read-package-tree</name>
        <version>5.2.2</version>
        <license>ISC License (ISC)</license>
        <repository>git+https://github.com/npm/read-package-tree.git</repository>
        <author>Isaac Z. Schlueter</author>
        <homepage>https://github.com/npm/read-package-tree</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/read-package-tree</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>8</id>
        <name>spdx-expression-parse</name>
        <version>3.0.0</version>
        <license>MIT License (MIT)</license>
        <repository>git+https://github.com/jslicense/spdx-expression-parse.js.git</repository>
        <author>Kyle E. Mitchell</author>
        <homepage>https://github.com/jslicense/spdx-expression-parse.js#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/spdx-expression-parse</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>9</id>
        <name>spdx-license-list</name>
        <version>6.0.0</version>
        <license>Creative Commons Zero v1.0 Universal (CC0-1.0)</license>
        <repository>git+https://github.com/sindresorhus/spdx-license-list.git</repository>
        <author>Sindre Sorhus</author>
        <homepage>https://github.com/sindresorhus/spdx-license-list#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/spdx-license-list</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>10</id>
        <name>table</name>
        <version>5.4.1</version>
        <license>BSD 3-Clause &quot;New&quot; or &quot;Revised&quot; License (BSD-3-Clause)</license>
        <repository>git+https://github.com/gajus/table.git</repository>
        <author>Gajus Kuizinas</author>
        <homepage>https://github.com/gajus/table#readme</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/table</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
    <dependency>
        <id>11</id>
        <name>yargs</name>
        <version>13.2.4</version>
        <license>MIT License (MIT)</license>
        <repository>git+https://github.com/yargs/yargs.git</repository>
        <author/>
        <homepage>https://yargs.js.org/</homepage>
        <path>/Users/morficus/workspace/license-ls/node_modules/yargs</path>
        <dependencyLevel>production</dependencyLevel>
    </dependency>
</dependencies>

```

### XML Output #2
```npx license-ls --depth=0 --format=xml --xml.asAttrs```
```xml
<dependencies>
    <dependency id="0" version="2.1.0" license="MIT License (MIT)" repository="git+https://github.com/avajs/ava.git" author="" homepage="https://avajs.dev" path="/Users/morficus/workspace/license-ls/node_modules/ava" dependencyLevel="development">ava</dependency>
    <dependency id="1" version="4.1.1" license="MIT License (MIT)" repository="git://github.com/visionmedia/debug.git" author="TJ Holowaychuk" homepage="https://github.com/visionmedia/debug#readme" path="/Users/morficus/workspace/license-ls/node_modules/debug" dependencyLevel="development">debug</dependency>
    <dependency id="2" version="4.5.1" license="MIT License (MIT)" repository="git+https://github.com/zemirco/json2csv.git" author="Mirco Zeiss" homepage="https://github.com/zemirco/json2csv#readme" path="/Users/morficus/workspace/license-ls/node_modules/json2csv" dependencyLevel="production">json2csv</dependency>
    <dependency id="3" version="1.5.0" license="MIT License (MIT)" repository="git://github.com/davidcalhoun/jstoxml.git" author="David Calhoun" homepage="http://github.com/davidcalhoun/jstoxml" path="/Users/morficus/workspace/license-ls/node_modules/jstoxml" dependencyLevel="production">jstoxml</dependency>
    <dependency id="4" version="2.0.1" license="ISC License (ISC)" repository="git+https://github.com/npm/libnpm.git" author="Kat Marchán" homepage="https://github.com/npm/libnpm#readme" path="/Users/morficus/workspace/license-ls/node_modules/libnpm" dependencyLevel="production">libnpm</dependency>
    <dependency id="5" version="14.1.1" license="ISC License (ISC)" repository="git+ssh://git@github.com/istanbuljs/nyc.git" author="Ben Coe" homepage="https://github.com/istanbuljs/nyc#readme" path="/Users/morficus/workspace/license-ls/node_modules/nyc" dependencyLevel="production">nyc</dependency>
    <dependency id="6" version="3.4.0" license="MIT License (MIT)" repository="git+https://github.com/sindresorhus/ora.git" author="Sindre Sorhus" homepage="https://github.com/sindresorhus/ora#readme" path="/Users/morficus/workspace/license-ls/node_modules/ora" dependencyLevel="production">ora</dependency>
    <dependency id="7" version="5.2.2" license="ISC License (ISC)" repository="git+https://github.com/npm/read-package-tree.git" author="Isaac Z. Schlueter" homepage="https://github.com/npm/read-package-tree" path="/Users/morficus/workspace/license-ls/node_modules/read-package-tree" dependencyLevel="production">read-package-tree</dependency>
    <dependency id="8" version="3.0.0" license="MIT License (MIT)" repository="git+https://github.com/jslicense/spdx-expression-parse.js.git" author="Kyle E. Mitchell" homepage="https://github.com/jslicense/spdx-expression-parse.js#readme" path="/Users/morficus/workspace/license-ls/node_modules/spdx-expression-parse" dependencyLevel="production">spdx-expression-parse</dependency>
    <dependency id="9" version="6.0.0" license="Creative Commons Zero v1.0 Universal (CC0-1.0)" repository="git+https://github.com/sindresorhus/spdx-license-list.git" author="Sindre Sorhus" homepage="https://github.com/sindresorhus/spdx-license-list#readme" path="/Users/morficus/workspace/license-ls/node_modules/spdx-license-list" dependencyLevel="production">spdx-license-list</dependency>
    <dependency id="10" version="5.4.1" license="BSD 3-Clause &quot;New&quot; or &quot;Revised&quot; License (BSD-3-Clause)" repository="git+https://github.com/gajus/table.git" author="Gajus Kuizinas" homepage="https://github.com/gajus/table#readme" path="/Users/morficus/workspace/license-ls/node_modules/table" dependencyLevel="production">table</dependency>
    <dependency id="11" version="13.2.4" license="MIT License (MIT)" repository="git+https://github.com/yargs/yargs.git" author="" homepage="https://yargs.js.org/" path="/Users/morficus/workspace/license-ls/node_modules/yargs" dependencyLevel="production">yargs</dependency>
</dependencies>
```

## Using as a library
You can use all of the same CLI options when using `license-ls` as a module (with the exception of anything that is specific to out format - such as `include` or `format`).  
When using it as a module, the function will always return a promise that resolves to an Array and will include all properties (`['id', 'name', 'version', 'license', 'repository', 'author', 'homepage', 'path', 'dependencyLevel']`)

```javascript
const licenseLs = require('license-ls')
const options = {
    depth: 1,
    prod: true
}

licenseLs(options)
.then(result => {
    // do your thing
})
```

## Contributing
Want a new feature added? Found a bug?
Go ahead an open [a new issue](https://github.com/morficus/license-ls/issues/new) or feel free to submit a pull request
