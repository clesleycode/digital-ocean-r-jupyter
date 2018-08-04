
### Introduction

Jupyter Notebook is a commonly used tool in data science because of its interactive nature and ability to be used across different languages. Since Jupyter Notebook was first built for Python, it's first installed through the Python programming language. 

This tutorial will walk you through setting up Jupyter Notebook to be able to use R, another powerful statistical language often used in data science. By the end of this guide, you will be able to run R code using the Jupyter Notebook running on a local machine or remote server.

## Prerequisites

Before you begin this guide you'll need the following:

- [How to Install R](https://www.digitalocean.com/community/tutorials/how-to-install-r-on-ubuntu-16-04-2)
- [How to Setup Jupyter Notebook with Python3](https://www.digitalocean.com/community/tutorials/how-to-set-up-jupyter-notebook-for-python-3)


We will soon submit the IRkernel package to CRAN. Until then, you can install it via the devtools package:


```R
install.packages('devtools')
```

```
[secondary_label Output]
    Installing package into ‘/usr/local/lib/R/3.4/site-library’
    (as ‘lib’ is unspecified)
```

Once the `devtools` package is finished installing, you can continue the next step and install the `IRkernel`. You should expect a long output message since there are several components that need to be installed. 

```R
devtools::install_github('IRkernel/IRkernel')
```

```
[secondary_label Output]
    Downloading GitHub repo IRkernel/IRkernel@master
    from URL https://api.github.com/repos/IRkernel/IRkernel/zipball/master
    Warning message:
    “GitHub repo contains submodules, may not function as expected!”Installing IRkernel
    Installing digest
    '/usr/local/Cellar/r/3.4.1_2/lib/R/bin/R' --no-site-file --no-environ  \
      --no-save --no-restore --quiet CMD INSTALL  \
      '/private/var/folders/jm/8yfv_qsn2hx_g9rxkxfvsr_80000gn/T/RtmpvBbNmf/devtoolsb8c51b6b8be/digest'  \
      --library='/usr/local/lib/R/3.4/site-library' --install-tests 
    
    Installing IRdisplay
    Installing repr
    '/usr/local/Cellar/r/3.4.1_2/lib/R/bin/R' --no-site-file --no-environ  \
      --no-save --no-restore --quiet CMD INSTALL  \
      '/private/var/folders/jm/8yfv_qsn2hx_g9rxkxfvsr_80000gn/T/RtmpvBbNmf/devtoolsb8c4f457de0/repr'  \
      --library='/usr/local/lib/R/3.4/site-library' --install-tests 
    
    '/usr/local/Cellar/r/3.4.1_2/lib/R/bin/R' --no-site-file --no-environ  \
      --no-save --no-restore --quiet CMD INSTALL  \
      '/private/var/folders/jm/8yfv_qsn2hx_g9rxkxfvsr_80000gn/T/RtmpvBbNmf/devtoolsb8c143c40ec/IRdisplay'  \
      --library='/usr/local/lib/R/3.4/site-library' --install-tests 
    
    Installing pbdZMQ
    '/usr/local/Cellar/r/3.4.1_2/lib/R/bin/R' --no-site-file --no-environ  \
      --no-save --no-restore --quiet CMD INSTALL  \
      '/private/var/folders/jm/8yfv_qsn2hx_g9rxkxfvsr_80000gn/T/RtmpvBbNmf/devtoolsb8c69eecbc/pbdZMQ'  \
      --library='/usr/local/lib/R/3.4/site-library' --install-tests 
    
    Skipping install of 'repr' from a cran remote, the SHA1 (0.15.0) has not changed since last install.
      Use `force = TRUE` to force installation
    '/usr/local/Cellar/r/3.4.1_2/lib/R/bin/R' --no-site-file --no-environ  \
      --no-save --no-restore --quiet CMD INSTALL  \
      '/private/var/folders/jm/8yfv_qsn2hx_g9rxkxfvsr_80000gn/T/RtmpvBbNmf/devtoolsb8c5f195d91/IRkernel-IRkernel-97c492b'  \
      --library='/usr/local/lib/R/3.4/site-library' --install-tests 
  ```


Finally, to register the kernel in the current R installation, enter the following in your R kernel:


```R
IRkernel::installspec()
```

Once you have everything installed, you can start your Jupyter Notebook as you normally would by entering the following command on your terminal:

``` bash
jupyter notebook
```

This will trigger your browser to open up an interface that displays all the folders and files in your current directory. To access a Jupyter Notebook with an R kernel, you can make a new notebook by clicking on the "New" button, as shown below. Hover over and click "R" so a new window pops up. 

![Alt text for screen readers](https://imgur.com/6CdXBgo.png)

In the new Jupyter Notebook, you'll notice a major difference in the upper right hand corner. Instead of the usual Python logo is now the logo for R, indicating that this notebook uses the R kernel. 

![Alt text for screen readers](https://imgur.com/oRuFW51.png)

Now, if you want to switch programming languages for whatever reason (maybe you're working on an analysis that uses both Python and R), you can do that too. Under the "Kernel" tab, you'll find several options, including one to change your kernel. By clicking on a different language than your current language, you can restart your notebook to have it run code from another language.  

![Alt text for screen readers](https://imgur.com/2zQtXhp.png)

## Conclusion

Now you're ready to run some R code! 

![Jupyter Notebook cell that shows a print statement](https://imgur.com/GYjeA3o.png)