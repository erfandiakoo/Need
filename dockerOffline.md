sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.gpg > /dev/null
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get download docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

cp /media/usb/*.deb /tmp/

sudo dpkg -i /tmp/*.deb

sudo apt-get install -f

sudo systemctl start docker
sudo systemctl enable docker

sudo docker --version
sudo docker run hello-world
--get .deb docker packge and copy to new server
ls /var/cache/apt/archives | grep docker
scp docker-buildx-plugin_*.deb docker-ce_*.deb docker-ce-cli_*.deb docker-ce-rootless-extras_*.deb docker-compose-plugin_*.deb user@offline-server:/path/to/destination/

--install on new server
sudo dpkg -i /path/to/destination/docker-buildx-plugin_*.deb /path/to/destination/docker-ce_*.deb /path/to/destination/docker-ce-cli_*.deb /path/to/destination/docker-ce-rootless-extras_*.deb /path/to/destination/docker-compose-plugin_*.deb





