# Scripts

* **n2assembly**:

  Create a assembly build (a *.tar.gz that's installed in Docker or on a server).

  Syntax: `n2assembly CUSTOMER [ARGS]...`

  Example: `n2assembly agogis`


* **n2build**:

  Description: Build Nice2

  Syntax: `n2build {CUSTOMER|--} [ARGS]...`

  Example 1: `n2build agogis` (build customer agogis)

  Example 2: `n2build` (build all customers)

  Example 3: n2build -- clean (clean build for all customers, -- → all customer, ARGS are forwarded to mvn)
