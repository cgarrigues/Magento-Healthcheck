# Magento-Healthcheck
ruby script to perform a health check of a magento system

Script is not yet ready for prime time and there are many things which are not yet being scanned.

Pull down and execute the script using

```bash
wget -N https://github.com/cgarrigues/Magento-Healthcheck/raw/master/healthcheck
chmod +x healthcheck
./healthcheck
```

The output of the script include ANSI escape characters.  If you view the output through less, you will want to use the -r flag:

```bash
./healthcheck | less -r
```

You can also only look at lines that may be of concern with the --quiet flag:

```bash

./healthcheck --quiet
```

To send information to Magento support, use the --verbose option and compress the output into a file and attach that file to the ticket.

```bash
./healthcheck --verbose | bzip2 > $HOSTNAME-health.bz2
```


Updates and additions to the code in the form of Pull Requests are much appreciated.
