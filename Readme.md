# luke catalog

A collection of official luke modules.

## How to use modules from here


You can directly load your required module remotely from this repo or use it locally:

```luke
use https://raw.githubusercontent.com/luke-lang/luke-catalog/master/modules/<MODULE.js>

use path/to/<MODULE>.js

 
//If you install this package via npm in the same directory (`npm i luke-catalog`), you can use the shortcut access:

use $catalog/<MODULE.js>
```

(`$catalog` will actually resolve the actual path to the node module)

# Modules

## default (built in)

***use {module}***

Use a module. {module can either be a local file or loaded over https}

```luke
use example.luke.js

use https://domain.com/example.luke.js
```

***ns {namespace}***

Set a namespace context. Namespace contexts will be active until another `ns`is set or the script ends.

```luke
ns example;
```

***print {text}***

Prints something. `{text}`can be of any type.

```luke
print "Hello World"
```

***list ...***

***commands***

Lists avilable commands for the current namespace.

```luke
list commands;
```

***modules***

Lists all used modules

```luke
list modules;
```


***download {url}***

Downloads a file

```luke
download https://google.com;
```

***install {npm-package}***

Installs an npm package into the current directory

```luke
install express
```



## Rest

A module to emit basic REST commands to any url.


***POST {data} to {url}***

Emit a post request

```luke
POST {username: "Peter", password: "pass"} to https://api.com/auth
```

***PATCH {data} to {url}***

Emit a patch request

```luke
PATCH {username: "Nicole"} to https://api.com/person
```

***PUT {data} to {url}***

Emit a put request

```luke
PUT {username: "Luke"} to https://api.com/person
```

***GET {query} from {url}***

Emit a get request

```luke
GET username=Nicole from https://api.com/persons
```



## objy

A module for building object-driven programs. In objy everyting is a behaviour-driven object, which controls and observes itself.

Full example:

```luke
use objy.luke.js;

define obbjectFamily with name car and pluralName cars;

add car with name "Mercedes";

get cars with name "Mercedes";

update car "id123" set name "Chevrolet";
```

***define objectFamily***

Define an object family.

```luke
define objectFamily with name car and pluralName cars
```

***add {object} {data}***

Add an object

```luke
add car with name "Mercedes" and color "silver";

// or

add car {name: "Mercedes", color: "silver"}
```

***get {object} {id}***

Get a single object

```luke
get car "id123";
```

***get {objects} {query}***

Get multiple objects matching a query

```luke
get cars with name "Mercedes"

//or

get cars {name: "Mercedes"}
```





# Add your module

In order to add your module to this repo you must meet the following constraints:

* Module name must be: <MODULENAME>.luke.js
* Modules must be single files
* Modules must be added to the modules folder of this repo
* A proper module documentation must be added to the readme file

***Module documentation format:***

Under `#modules`

```
## <MODULE NAME>

<MODULE DESCRIPTION>

### <token> <params>

<TOKEN DESCRIPTION>

<CODE EXAMPLE>
```
