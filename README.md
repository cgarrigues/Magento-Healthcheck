# Magento-Healthcheck
ruby script to perform a health check of a magento system

Note that some Magento systems do not have ruby installed, so you may have to install ruby first. (an aside: I am not prepared to rewrite this in php, sorry; if you want to do that, have at it.)

There are still many items that are not scanned by the script, but it runs reliably and with low impact.

Pull down and execute the script using

```bash
wget -N https://github.com/cgarrigues/Magento-Healthcheck/raw/master/healthcheck
chmod +x healthcheck
./healthcheck
```


Note that although it can collect some data if not run as root, running as root will provide a more thorough report, so please run it that way if possible.

The output of the script include ANSI escape characters.  If you view the output through less, you will want to use the -R flag:

```bash
./healthcheck | less -R
```

You can also only look at lines that may be of concern with the --quiet flag:

```bash
./healthcheck --quiet
```
Or with the --verbose flag, to see extra information.

```bash
./healthcheck --verbose
```

To send information to Magento support, compress the output into a file and attach that file to the ticket.

```bash
./healthcheck | bzip2 > $HOSTNAME-health.bz2
```

Do this on all involved servers including web, DB, and caching servers. Magento may possibly ask for the --verbose option.

In a test or dev environment, you may have Magento Roots which are located below the document root.  To locate those, use the --findroots option:

```bash
./healthcheck --findroots
```

Also, you can specify the location of one or more magento roots with the --root option:

```bash
./healthcheck --root=/home/user/dev/1234 --root=/home/user2/dev/5678
```

Updates and additions to the code in the form of Pull Requests are much appreciated. At the present time, please code to ruby-1.x standards, rather than 2.x.
