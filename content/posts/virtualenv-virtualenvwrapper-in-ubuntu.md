+++ 
date = "2019-08-20"
title = "Configuring virtualenv and virtualenvwrapper in ubuntu"
slug = "virtualenv-virtualenvwrapper-in-ubuntu" 
tags = ["hugo", "i18n"]
categories = ["blog"]

+++

We all must have faced the situation where version of our packages don't match and takes up hours of our time to get solved. A virtual Environment is an isolates working environment of a Python project so that other projects aren't hampered.

So, lets start the configuration with __virtualenv__. To install it via pip
```
$ pip install virtualenv
```

See, it is as simple as that. Now, you can work in an isolated python3.6 project and also in an isolated python3.7 project without affecting each other. Let's explore it's usages and how it is done:

1. To make a virtualenv:
```
$ virtualenv testEnv
```

2. To initiate the virtualenv
```
$ source testEnv/bin/activate
```
Note: to run this 
3. To deactivate the environment
```
$ deactivate
```

But wait, there's more to it. There's another amazing additive layer of __virtualenvwrapper__ that makes you task much easier and convenient. 
To install it:
```
$ pip install virtualenvwrapper
```

and then and add following lines to your .bashrc file that must be in your __/home__
```
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
export WORKON_HOME=~/Envs
source /usr/local/bin/virtualenvwrapper.sh
```
Note: 'Envs' is the name of directory and you can choose any name for you.

And finally, to reload the bashrc and to apply the changes instantly run in your terminal
```
source ~/.bashrc
```

Now you can simply run
```
$ mkvirtualenv testEnv
```
to create a virtualenv. Aditionally, you can specify the python version yourself by 
```
$ mkvirtualenv --python=python2 testEnv2
```

__virtualenvwrapper__ enables you to activate the environment by by a simple keyword 'workon' followed by the environment name. 
```
workon testEnv
```
