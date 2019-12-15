# Install and Configure Flume

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/flume/1.9.0/apache-flume-1.9.0-bin.tar.gz
tar -zxvf apache-flume-1.9.0-bin.tar.gz
sudo mkdir /usr/local/flume
sudo mv apache-flume-1.9.0-bin /usr/local/flume
sudo ln -s /usr/local/flume/apache-flume-1.9.0-bin /opt/flume
```

Replace below files with files in `/opt/flume/conf`
[flume-env.sh](../flume/flume-env.sh)

```bash
echo '# Flume' >> ~/.bashrc
echo 'export FLUME_HOME=/opt/flume' >> ~/.bashrc
echo 'export PATH=$PATH:$FLUME_HOME/bin' >> ~/.bashrc
source ~/.bashrc
flume-ng help
```

**Expected result**

```bash
Usage: /opt/flume/bin/flume-ng <command> [options]...

commands:
  help                      display this help text
  agent                     run a Flume agent
  avro-client               run an avro Flume client
  version                   show Flume version info

global options:
  --conf,-c <conf>          use configs in <conf> directory
  --classpath,-C <cp>       append to the classpath
  --dryrun,-d               do not actually start Flume, just print the command
  --plugins-path <dirs>     colon-separated list of plugins.d directories. See the
                            plugins.d section in the user guide for more details.
                            Default: $FLUME_HOME/plugins.d
  -Dproperty=value          sets a Java system property value
  -Xproperty=value          sets a Java -X option

agent options:
  --name,-n <name>          the name of this agent (required)
  --conf-file,-f <file>     specify a config file (required if -z missing)
  --zkConnString,-z <str>   specify the ZooKeeper connection to use (required if -f missing)
  --zkBasePath,-p <path>    specify the base path in ZooKeeper for agent configs
  --no-reload-conf          do not reload config file if changed
  --help,-h                 display help text

avro-client options:
  --rpcProps,-P <file>   RPC client properties file with server connection params
  --host,-H <host>       hostname to which events will be sent
  --port,-p <port>       port of the avro source
  --dirname <dir>        directory to stream to avro source
  --filename,-F <file>   text file to stream to avro source (default: std input)
  --headerFile,-R <file> File containing event headers as key/value pairs on each new line
  --help,-h              display help text

  Either --rpcProps or both --host and --port must be specified.

Note that if <conf> directory is specified, then it is always included first
in the classpath.
```
