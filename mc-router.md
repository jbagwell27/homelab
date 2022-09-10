# MC-Router

A MC-Router proxy implementation built as a systemd service in an LXC Container.  
Taken from [itzg/mc-router](https://github.com/itzg/mc-router)

## Environment

I am running this in a Debian 11 LXC container on Proxmox 7.2, however, these steps should be universal across platforms.

## Steps

1.  Download and extract the latest release binary from [itzg/mc-router](https://github.com/itzg/mc-router).

    >Note: Make sure you put the files in a sensible location. They will be referenced by their absolute path

    ```
    mkdir mc-router
    wget -O mc-router.tar.gz https://github.com/itzg/mc-router/releases/download/1.16.1/mc-router_1.16.1_linux_amd64.tar.gz 
    tar -xf mc-router.tar.gz -C mc-router
    ```

2.  Create 2 files: 

    -   An environment file `/etc/vanilla`
    
        ```ini
        MAPPING="vanilla.domain.com=192.168.1.25:25565"
        ```

    -   And a systemd service file: `/etc/systemd/system/mc-router@.service`

        > The `@` in the filename may look weird, but it is necessary.

        ```ini
        [Unit]
        Description=Minecraft proxy service (%i)
        After=network.target
        StartLimitIntervalSec=0

        [Service]
        Type=simple
        Restart=on-failure
        RestartSec=5s
        EnvironmentFile=/etc/%i
        ExecStart=/path/to/file/mc-router MAPPING

        [Install]
        WantedBy=multi-user.target
        ```

        The `%i` references the filename that we call after the `@`.
     

3.  Start the Service.

    The `@` in the file name is used to dynamically reference different servers and domains. In this case we made a file `vanilla` so we will use that
    
    
    ```
    systemctl start mc-router@vanilla
    ```

    Enable it so that it runs at startup:

    ```
    systemctl enable mc-router@vanilla
    ```

You can do this with different environment files for different servers: vanilla, feed-the-beast, bucket, paper, etc.  
All you'll need to do is make a new environment file and use it in the name of the service