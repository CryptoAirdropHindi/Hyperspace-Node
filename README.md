# Hyperspace Node
## ➡️ Method 1. Browser Node
* Run using browser if you have an idle PC or during the times you're working on your computer
* You might obtain uptime for multipliers, I'm running it 24/7
* You can run it on a windows server (if you have a VPS with windows installed on for other extension nodes)

### 1. Visit: https://node.hyper.space/

### 2. Switch the red button to green

![image](https://github.com/user-attachments/assets/727b0c1e-031b-4f5c-9bb6-60a4becaf19b)

### 3. Check your points

![Screenshot_516](https://github.com/user-attachments/assets/3697612a-9ee6-4d7e-837c-f74d5cbacf8d)
![Screenshot_517](https://github.com/user-attachments/assets/6682b24d-224e-4e4c-96d3-4961a024eb77)

* You receive points based on your node's uptime, liveness multiplier, and your system specification's tier
* You initially get Tier-5 but your tier and multiplier will increase over time as your node stays online with good performance

### 4. Save your *PrivateKey*
You can import it later

![Screenshot_518](https://github.com/user-attachments/assets/3e08837d-1261-4873-b038-e7f86222d1b2)
![Screenshot_519](https://github.com/user-attachments/assets/67506c7d-9932-462c-a4d0-29f3992d7e4a)

❗️* **Make sure to keep the red switch turned on because it can sometimes disconnect, possibly because of network issues.**

#

## ➡️ Method 2. Download App (Windows, Linux, Mac)
### 1. Visit: https://hyper.space/downloads
You can choose GPU or CPU versions

![Screenshot_520](https://github.com/user-attachments/assets/45db8805-a579-489a-ad87-14f011332c4e)

### 2.Download a model and toggle on the red button

![image](https://github.com/user-attachments/assets/e79f90f3-7c50-4a8c-a352-712844592092)

* You can find your PrivateKey file `key.pmf` in this directory `C:\Users\XXX\AppData\Roaming\hyperspace`

#

## ➡️ Method 3. Linux CLI Node (VPS)
* I'm receiving points on my VPS by going through the following guide but I will update the repo if it was needed to enhance it
* You can also check out [Official repository](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file) for more commands and info

### Install
```
curl https://download.hyper.space/api/install | bash

source /root/.bashrc
```

### Start your node
```console
# Create a screen ro run it in background for later
screen -S hyperspace

# Run node
aios-cli start
```
* To continue, minimize your screen using `CTRL+A+D` or Open second terminal
* Turn back to screen: `screen -r hyperspace`

### Config Node
```console
# Run this to see what models are required
aios-cli hive select-tier 5
# Download a required model
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
# Import your private key - Create a my.pem file using nano .pem and input a privatekey (You can get a privatekey from browser version)
aios-cli hive import-keys ./my.pem
# Set those keys as the preferred keys for this session
aios-cli hive login
# Make sure the model is registered
aios-cli hive connect
aios-cli hive select-tier 5
```

### Check Points
```
# To check your current multiplier and points
aios-cli hive points
```

![Screenshot_514](https://github.com/user-attachments/assets/b840775e-6c58-4fe4-bd95-a5b876ba7de5)


# Usefull commands
```console
# Shortcut for Start, Login and Connect to Hive commands, if you've stopped you node
aios-cli start --connect
# Update node
aios-cli version
# Stop node
aios-cli kill
```
