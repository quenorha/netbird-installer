# Netbird Installer

This shell script will install the [Netbird](https://netbird.io) Client.

For some reasons, the /var/log/netbird folder can't be created on service startup, therefore the install.sh was modified in order to add the folder created in the /etc/init.d/netbird script.

You can pass the shell script arguments to allow it to do more things automaticly.

| Shorthand | Longhand | Default | Description |
| --- | --- | --- | --- |
| -h | --help | | Show Help |
| -ia | --install-app | true | Install Netbird Binary |
| -iui | --install-ui | false | Install Netbird UI Binary |
| -iv | --install-version | latest | Target Install Version |
| -d | --docker | false | Install Netbird in Docker |
| -ns | --no-service | false | Don't install and start service |
| -np | --no-preconfigure | false | Don't preconfigure Netbird |
| -b | --base-url | https://github.com/netbirdio/netbird/releases/download | Base URL for binary downloads (Allows script to be used in Air-Gapped Systems) |
| -m | --management-url | https://api.wiretrustee.com:33073 | Management URL (Defaults to Netbird SaaS) |
| -sk | --setup-key | | Setup Key |
| -q | --quiet | false | Don't prompt to confirm install |
| -dn | --docker-name | netbird | Set Docker Container Name |
| -dh | --docker-hostname | hostname | Set Docker Hostname |

# Setup

SSH into the device.

If installing on a WAGO device go to the /home directory before downloading and running the script

```bash
cd /home
```

To do a fully automated install you could run the following:

```bash
curl -OLsk https://raw.githubusercontent.com/quenorha/netbird-installer/main/install.sh && sudo bash install.sh --quiet
```

If you have prepared a setup key in the Netbird admin console, you can set it up using --setup-key parameter : 
```bash
curl -OLsk https://raw.githubusercontent.com/quenorha/netbird-installer/main/install.sh && sudo bash install.sh --quiet --setup-key=ABCDEFGH-1234-5678-ABCD-EFGHIJKLM
```


![images/screenshot.png](images/screenshot.png)
