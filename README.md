### Memcached 注释

####说明

#### Memcached说明
Base On v1.4.20(2014-5-11)


华丽的分割线
=============================================================
# Memcached

## 依赖关系

* libevent, http://www.monkey.org/~provos/libevent/ (libevent-dev)

## 环境

### Linux

如果使用Linux，需要支持epoll的内核, libevent 在select下也可以运行，但很差。

Linux 2.4不支持epoll， 但可以通过反向移植实现

    http://www.xmailserver.org/linux-patches/nio-improve.html
需要epoll-lt patch (level-triggered).

### Mac OS X

如果使用MacOS, 需要libevent 1.1 或更高版本来回避 kqueue BUG

Also, be warned that the -k (mlockall) option to memcached might be
dangerous when using a large cache.  Just make sure the memcached machines
don't swap.  memcached does non-blocking network I/O, but not disk.  (it
should never go to disk, or you've lost the whole point of it)

## 网站

* http://www.memcached.org
