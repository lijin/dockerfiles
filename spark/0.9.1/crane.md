Readme for crane.yaml
=====================

For use with [crane](https://github.com/michaelsauter/crane) to run the Spark cluster.

Usage
-----

1. Start skydns
2. Start skydock
3. Start master
4. Start worker

```bash
$ sudo crane run -g skydns
$ sudo crane run -g skydock
$ sudo crane run -g master
$ sudo crane run -g worker
```
