# (PART - 2) Configuration and The environment

## The environment

### Examining the environment

``printenv`` => Display envrionment variables.

### How is the Environment Established?

#### A login shell session:
This is one in which we are prompted for our username and password. This happens when we start a virtual console session.

##### Startup Files for a login shell sesion
-   /etc/profile
-   ~/.bash_profile
-   ~/.bash_login
-   ~/.profile

#### A non-login shell session

This typically occurs when we launch a terminal session in GUI.

##### Startup files for non-login shell sessions
-   /etc/bash.bashrc
-   ~/.bashrc

## A Gentle Introduction

### If you get lost in vim, you can press ESC twice. 

You can delete line by pressing ``dd``.

You can search text with ``/`` like ``less``

You can open multiple files with ``vim``.

You can paste by pressing ``p``.

## Customizing Prompt

You can customize prompt. 

![PS](images/prompt_string.png)



