---
layout: post
title: Package Introduction - prodigy
category: emacs
tags: [emacs, package]
---
Prodigy: Manage External Services From Within Emacs.

[Github Repo](https://github.com/rejeep/prodigy.el)

When we are writing programs or documents, we may need to start some services in background. Take my blog writting for example. I use jekyll as static-site-generator which generates new HTML when saving the file. Before using prodigy, I need to start jekyll in another terminal (by ``jekyll serve -w``).

Other dynamic updating service, or programs that need to be tested continually (e.g. django server), You can use prodigy to manage the excution job for you!

## Basic Information:
1. Installation:
    1. El-get: ``M-x el-get-install <RET> prodigy``
    2. Package.el ``M-x install-package <RET> prodigy``
2. Usage: User should define the options first.
    - Services: ``M-x describe-variable <RET> prodigy-services``
3. Define service and manage the service group
    - ``(prodigy-define-service (&rest args))``
    - You can even add tags and filters to your service to start multiple services in one click.
	- A service definition schema:
``` lisp
	(setq prodigy-services
	 '((:prop value ...)
```
## My jekyll service settings:

``` lisp
(prodigy-define-tag
    :name 'jekyll
    :env '(("LANG" "en_US.UTF-8")
	       ("LC_ALL" "en_US.UTF-8")))
;; You should add env varible when defining a tag.

(prodigy-define-service
    :name "Jekyll server"
    :command "jekyll"
    :args '("serve" "-w")
    :cwd "/home/haroldwu/yfwu.github.io"
    :tags '(jekyll)
    :kill-signal 'sigkill)
```
## Start Using Prodigy
1. Type ``M-x prodigy`` to enter dashboard.
2. Type ``M-x prodigy-start`` or move cursor to the service you want to start and strike ``s``
