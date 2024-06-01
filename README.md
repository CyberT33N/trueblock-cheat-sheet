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
```
