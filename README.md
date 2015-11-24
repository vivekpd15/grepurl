# grepurl

URL links grepper / crawler

## Usage

```
$ grepurl -h
URL links grepper / crawler
Usage: ./grepurl [OPTION]... URL...

Options:
  -h            display this help and exit
  -a            grep only URLs inside <a> tags
  -i            grep only URLs inside <img> tags
                (by default, both <a> and <img> tags are processed)
  -r <regexp>   return only URLs matching '<regexp>'
  -d            download resources
  -o <dir>      store downloaded resources inside '<dir>'
```

## Example

### Grep

```
# list http://foutaise.org images
$ grepurl -i http://foutaise.org
http://foutaise.org/static/img/fa-home.png
http://foutaise.org/static/img/yehuda.gif
http://foutaise.org/static/img/lisp-logo.jpg
```

### Crawl

```
# retrieve http://foutaise.org images
$ mkdir imgs
$ grepurl -i -d -o imgs http://foutaise.org
http://foutaise.org/static/img/fa-home.png
http://foutaise.org/static/img/yehuda.gif
http://foutaise.org/static/img/lisp-logo.jpg
Downloading http://foutaise.org/static/img/fa-home.png as imgs/fa-home.png
Downloading http://foutaise.org/static/img/lisp-logo.jpg as imgs/lisp-logo.jpg
Downloading http://foutaise.org/static/img/yehuda.gif as imgs/yehuda.gif
```
