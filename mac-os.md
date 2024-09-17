# Mac OS

## ZSH
Loading Order: `.zshenv` → `.zprofile` → `.zshrc` → `.zlogin` → `.zlogout`
- `.zprofile` - Set the environment for login shells
- `.zshrc` - sets the environment for interactive shells


File `./zshrc`
```shell
export JAVA_HOME=$(/usr/libexec/java_home -v17); # Default 17


menu() {
    echo 'jdk $1   - Switch JDK version';
    echo 'jdkls    - List JDK versions';
    echo 'ports    - List busy ports';
}

# Java
jdk() {
    version=$1
    unset JAVA_HOME;
    export JAVA_HOME=$(/usr/libexec/java_home -v"$version");
    java -version
}

jdkls() {
    /usr/libexec/java_home -V
}


# Network tools
ports() {
    lsof -i -n -P | grep TCP | grep LISTEN
}
```

## Other
```shell
# Remove Node
sudo rm -rf /usr/local/bin/node
sudo rm -rf /usr/local/bin/npm
sudo rm -rf /usr/local/lib/node_modules
sudo rm -rf /usr/local/lib/dtrace/node.d
sudo rm -rf /usr/local/share/man/man1/node
sudo rm -rf /Users/$USER/.npm
```

