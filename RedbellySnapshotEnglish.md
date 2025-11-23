<img width="1200" height="300" alt="517080857-13a15c9f-5a54-4c46-b075-a23d50ea5fa1" src="https://github.com/user-attachments/assets/5536943a-e29a-4dfd-b2e6-54177745af57" />

Install your Redbelly node using the standard installation process. Once the installation is complete and your node begins syncing, continue with the setup by running the commands listed below.

This snapshot will start your node from block 2,633,535, allowing you to skip the initial full synchronization.

------

1- Stop the Redbelly service.

```Sieve
sudo systemctl stop redbelly.service
```

2- Back up your ```nodekey``` file.

```Sieve
sudo mv /opt/redbelly/rbn/database/nodekey /opt/redbelly/rbn/nodekey
```

3- Remove the old database directory.

```Sieve
sudo rm -rf /opt/redbelly/rbn/database
```

4- Download the snapshot and extract it into the directory.

```Sieve
curl -L http://redbellysnapshot.lorentochain.online/redbelly/redbelly-snapshot.tar.gz | sudo tar -xz -C /opt/redbelly/rbn
```

5- After the snapshot extraction is complete, restore your ```nodekey``` file.

```Sieve
sudo mv /opt/redbelly/rbn/nodekey /opt/redbelly/rbn/database/nodekey
```

6- Start the Redbelly service again.

```Sieve
sudo systemctl start redbelly.service
```

7- Check the service status to ensure the node is running correctly.

```Sieve
systemctl status redbelly.service
```
