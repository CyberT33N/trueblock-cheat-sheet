# trueblock-cheat-sheet
- **https://trueblocks.io/docs/install/install-core/


# Install
```
sudo apt-get install cmake libcurl4-openssl-dev

# Custom version
wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz
sudo tar -xvf go1.22.3.linux-amd64.tar.gz -C /usr/local
echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.profile 
source ~/.profile 

cd ~/Projects
git clone --depth 1 --no-single-branch --recurse-submodules --branch develop https://github.com/TrueBlocks/trueblocks-core
cd trueblocks-core
mkdir build && cd build
../scripts/go-work-sync.sh
cmake ../src
make

# add bin to path
sudo gedit ~/.zshrc  
export PATH="$PATH:/home/usrname/Projects/trueblocks-core/bin"

# Get config path
chifra config --paths

# added config
sudo gedit /home/usrname/.local/share/trueblocks/trueBlocks.toml
```
- Edit this file and locate the [chains.mainnet] section. Add a valid RPC endpoint. If you don’t know what this means, search Google.  
```shell
[chains.mainnet]
rpcProvider = "http://localhost:8545"
# https://mainnet.infura.io/v3/xxxxxxxxxxxxxxxxx
```
- **Will not work with free infura api key because you get error too many requests. Make sure to host your own node e.g. with geth**
  
- If you wish to use the --articulate feature (you probably do), add an API key to the following section:
```
[keys.etherscan]
apiKey = "<your Etherscan api key>"   # optional
```

- Run to verify if everything works:
```
chifra blocks 12
```







<br><br>
<br><br>
___________________________________________
___________________________________________
<br><br>
<br><br>

# Get transactions from address
```
chifra init
chifra export addressHere
```
