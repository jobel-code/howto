# Remove all stoped docker containers

    docker ps -a |xargs docker rm
    
# How to remove all orphans docker images 
[source](https://forums.docker.com/t/command-to-remove-all-unused-images/20/4)

    docker rmi -f $(docker images | grep "<none>" | awk "{print \$3}")

# how to install the R-kernel and the orientdb package ubuntu 16.04

follow this blog [Jupyter And R Markdown: Notebooks With R](https://www.datacamp.com/community/blog/jupyter-notebook-r#alternatives) but first look make sure you have installed the following packages to avoid the devtools installation error.


# Solving installation-of-package-devtools-had-non-zero-exit-status- ...

    sudo apt-get install libssl-dev  # need it to install both  'httr' and 'git2r'
    sudo apt-get -y install libcurl4-gnutls-dev libxml2-dev    # need for 'httr'

    install.packages(c('httr', 'git2r', 'repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))

    # install.packages('devtools', repos='http://cran.rstudio.com/')

solutions from [installing-devtools-fails-beacuse-of-dependency-but-dependency-is-not-available](https://stackoverflow.com/questions/35063883/installing-devtools-fails-beacuse-of-dependency-but-dependency-is-not-available)

and [installation-of-package-devtools-had-non-zero-exit-status-in-a-powerpc](https://stackoverflow.com/questions/31114991/installation-of-package-devtools-had-non-zero-exit-status-in-a-powerpc), however no need to be root.
# Solving `%%R ` magic not working
See [https://stackoverflow.com/questions/43682789/errorrootcell-magic-r-not-found](https://stackoverflow.com/questions/43682789/errorrootcell-magic-r-not-found)

This is a link to the best answer I have found to the problem given on this thread: [R Notebook](https://answers.dataiku.com/14/in-an-r-notebook-i-have-the-error-cell-magic-r-not-found).

This link states that the error means that R is not configured in your DSS instance. You need to install R manually.

The commands given on the forum post are:

Install the R packages RJSONIO and HTTR in any R console.
Install the Python package rpy2:

pip install rpy2

Afterward, they give the following link: [configure R](http://doc.dataiku.com/dss/latest/installation/r.html).

I hope this is helpful and well worded.
