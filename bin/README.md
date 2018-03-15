# Scripts

## Content

* [`n2assembly`](#command-n2assembly): Nice2 assembly build
* [`n2build`](#command-n2build): Build Nice2
* [`n2log-unscramble`](#command-n2log-unscramble): Make `oc logs -c nice …` readable

## Commands

### Command: `n2assembly`

Create a assembly build (a *.tar.gz that's installed in Docker or on a server).

#### Syntax

```
n2assembly [{CUSTOMER|--} [MAVEN_ARGS]...]
```

#### Example
  
Run assembly build for customer agogis:
  
```
n2assembly agogis
```


### Command: `n2build`

Build Nice2

### Syntax

```
n2build [{CUSTOMER|--} [MAVEN_ARGS]...]
```

#### Examples

Build customer agogis:

```
n2build agogis
```

Build all customers:

```
n2build
```

Run clean build for all customers (`--` = all customers):

```
n2build -- clean
```


### Command: `n2log-unscramble`

Unscramble (=make it human readable) output from `oc logs -c nice …`.

#### Syntax

```
log-unscramble [-h] [--ignore-case] [--file [FILE]] [--level {trace,info,warn,error}] [SEARCH_TERM]
```

#### Examples

Show all logs:

```
oc logs -c nice nice-1-1tjcp | n2log-unscramble
```

Show all logs from previous pod:

```
oc logs -p -c nice nice-1-1tjcp | n2log-unscramble
```

Show logs of severity WARN and higher:

```
oc logs -c nice nice-1-1tjcp | n2log-unscramble -l warn
```

Show logs of severity ERROR that contain the search term "ProgressPersistenceManager":

```
oc logs -c nice nice-1-1tjcp | n2log-unscramble -l error ProgressPersistenceManager
```
