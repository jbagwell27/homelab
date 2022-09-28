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

2.  Create an environment file `/etc/mcrouuter`
    
    ```ini
    MAPPING="vanilla.domain.com=192.168.1.25:25565,forge.domain.com=192.168.1.26:25565"
    ```
    Each entry is comma separated
    
3.  Create a systemd service file: `/etc/systemd/system/mc-router.service`

    ```ini
    [Unit]
    Description=Minecraft proxy service
    After=network.target
    StartLimitIntervalSec=0

    [Service]
    Type=simple
    Restart=on-failure
    RestartSec=5s
    EnvironmentFile=/etc/mcrouter
    ExecStart=/path/to/file/mc-router MAPPING

    [Install]
    WantedBy=multi-user.target
    ```
     

4.  Start the Service.
    
    ```
    systemctl start mc-router
    ```

    Enable it so that it runs at startup:

    ```
    systemctl enable mc-router
    ```

You can do this for different servers: vanilla, feed-the-beast, bucket, paper, etc.  
All you need to do is add to the environment file and reload the service.