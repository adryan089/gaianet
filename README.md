
![Logo](https://www.gaianet.ai/imgs/logo.png)


## Tutorial on running node from GAIANET

The essence of this tutorial is how to start a GAIANET node on a VPS using tmux briefly based on the tutorial from [GAIANET Documentation](https://github.com/GaiaNet-AI/gaianet-node)


## Instalation

a. Update & Upgrade Package

```bash
sudo apt-get update && sudo apt-get upgrade -y
```
b. Download TMUX

```bash
sudo apt-get install tmux
```
c. Download Source Code from server GAIANET
```bash
curl -sSfL 'https://raw.githubusercontent.com/GaiaNet-AI/gaianet-node/main/install.sh' | bash
``` 
_Downloading node files generally takes 10-15 minutes or even more depending on your server specifications._ By default the node files are in the ```$HOME/gaianet``` directory and if you want to place the node file into another directory use the following command :
```bash
curl -sSfL 'https://raw.githubusercontent.com/GaiaNet-AI/gaianet-node/main/install.sh' | bash -s -- --base $HOME/gaianet.alt
```
d. Open Tmux session
```bash
tmux new-session -s gaia
```
note : change the word **_gaia_** in the last command as you like.

e. Node initialization

```bash
gaianet init
```
<details><summary> The output should look like below: </summary>

```bash
[+] Downloading Llama-2-7b-chat-hf-Q5_K_M.gguf ...
############################################################################################################################## 100.0%############################################################################################################################## 100.0%

[+] Downloading all-MiniLM-L6-v2-ggml-model-f16.gguf ...

############################################################################################################################## 100.0%############################################################################################################################## 100.0%

[+] Creating 'default' collection in the Qdrant instance ...

    * Start a Qdrant instance ...

    * Remove the existed 'default' Qdrant collection ...

    * Download Qdrant collection snapshot ...
############################################################################################################################## 100.0%############################################################################################################################## 100.0%

    * Import the Qdrant collection snapshot ...

    * Recovery is done successfully
```

f. Start Node
```bash
gaianet start
```
you can see output :

```console
... ... https://0xf63939431ee11267f4855a166e11cc44d24960c0.us.gaianet.network
```
_The script prints the official node address on the console as follows. You can open a browser to that URL to see the node information and then chat with the AI agent on the node._



Finally, now your GAIANET node is running and you can close the terminal without fear of the node stopping.

### Other Command 

If you exit the terminal server, you can reopen it and see the log of the running GAIANET node.

use the following command :
```bash
tmux a -d -t gaia
```

note    : note : change the word **_gaia_** in the last command according to the command in step D.

You can also replace the tmux application with the screen application, but here I explain how to run node with the tmux application.
