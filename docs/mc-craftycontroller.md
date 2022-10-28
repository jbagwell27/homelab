# Minecraft forge in Crafty Controller

- Select Forge from the list of servers when adding

- After it runs once, you'll get an error: `X11 Display Variable not set` or something like that

- Go to the `config` tab and change the executable path to include `--installServer` at the end..

**Note:** `--installServer` is case sensitive.

- After that runs, Go through the ssh console and `chmod +x run.sh` as the `crafty` user.

- Change the full executable path in the web ui to be `./run.sh` 

- The server should run successfully.

**Note:** To install mods, manually download them to the `mods` folder
