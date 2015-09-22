# docker.virtuoso
Dockerized version of virtuoso.

### Source code

  - [github.com](http://github.com/ezyk/docker.virtuoso)

### Installation

  * Install [Docker](https://www.docker.com/).

### Clone repository
    $ git clone https://github.com/ezyk/docker.virtuoso
    $ cd docker.virtuoso

### Usage virtuoso 6

    $ docker run -d -p 1111:1111 -p 8890:8890 ervis/virtuos:6

### Usage virtuoso 7

    $ docker run -d -p 1111:1111 -p 8890:8890 ervis/virtuos:6

### Provide your own virtuoso.ini. Usage virtuoso 6

    $ docker run -d -v $(pwd)/virtuoso.ini.template:/opt/virtuoso-opensource/var/lib/virtuoso/db/virtuoso.ini -p 1111:1111 -p 8890:8890 ervis/virtuos:6


### Provide your own virtuoso.ini. Usage virtuoso 7

    $ docker run -d -v $(pwd)/virtuoso.ini.template:/opt/virtuoso-opensource/var/lib/virtuoso/db/virtuoso.ini -p 1111:1111 -p 8890:8890 ervis/virtuos:7
