# Update ATM

- Make a backup
**As Root**
```bash
systemctl stop minecraft
tar -cvf "/backups/atm8Full.$(date +"%Y.%m.%d").tar" /home/minecraft
# tar -cvf "/backups/atm8World.$(date +"%Y.%m.%d").tar" /home/minecraft/world

mv /home/minecraft/config{,.bak}
mv /home/minecraft/defaultconfigs{,.bak}
mv /home/minecraft/mods{,.bak}
mv /home/minecraft/kubejs{,.bak}
#mv /home/minecraft/libraries{,.bak}
```

- Download the latest server files
```bash
wget wget https://mediafilez.forgecdn.net/files/4135/843/Server-Files-1.0.5.zip
```

Pro tip: In Firefox you can copy the download link by right-clicking on the download file:  
![](https://github.com/jbagwell27/homelab/blob/main/docs/attachments/Copy-download-link.png)

- Extract the files and `cd` into the directory
```bash
unzip Server-Files-1.0.5.zip
cd Server-Files-1.0.5
```

If there is a forge update you'll need to update that version.
```bash
wget https://maven.minecraftforge.net/net/minecraftforge/forge/1.19.2-43.2.14/forge-1.19.2-43.2.14-installer.jar

java -jar forge-1.19.2-43.2.14-installer.jar --installServer
```
This will create a library folder inside the new server files.

**Any custom kubejs modifications will need to be restored. Hopefully those are in a separate `js` file**

- Copy new files

```bash
cp -R ./config /home/minecraft
cp -R ./defaultconfigs /home/minecraft
cp -R ./mods /home/minecraft
cp -R ./kubejs /home/minecraft
cp -R ./libraries /home/minecraft
