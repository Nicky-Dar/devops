# Install Node Exporter 

1. Download paket node exporter 
`wget https://github.com/prometheus/node_exporter/releases/download/v1.2.2/node_exporter-1.2.2.linux-amd64.tar.gz`

2. Extract package
`tar -xf node_exporter-1.2.2.linux-amd64.tar.gz`
3. Pindahkan hasil extract ke /usr/local/bin 
`sudo mv node_exporter-1.2.2.linux-amd64 /usr/local/bin
`
![image](https://user-images.githubusercontent.com/88620315/141654465-d8710d69-1b01-46ad-a006-f89aa2ece046.png)
4. Tambahkan user node_exporter 
`sudo useradd -rs /bin/false node_exporter`
5. Buat service node_exporter 
`sudo nano /etc/systemd/system/node_exporter.service`
Masukkan configurasi berikut:
 > [Unit]
>  Description=Node Exporter
>  After=network.target
> 
>  [Service]
>  User=node_exporter
>  Group=node_exporter
>  Type=simple
>  ExecStart=/usr/local/bin/node_exporter-1.2.2.linux-amd64/node_exporter
>  
>  [Install]
>  WantedBy=multi-user.target

6. Reload deamon
`sudo systemctl daemon-reload`

7. Enable service node exporter
`sudo systemctl enable node_exporter`

8. Start node exporter 
`sudo systemctl start node_exporter`

9. Cek status node exporter
`sudo systemctl status node_exporter.service`

![image](https://user-images.githubusercontent.com/88620315/141654741-93550a2c-2020-4078-914a-3b94497800d9.png)

# Install Prometheus
1.	Create Prometheus system group
`sudo groupadd --system Prometheus`
`sudo useradd -s /sbin/nologin --system -g prometheus prometheus
`
2.	Create data & configs directories for Prometheus
`sudo mkdir /var/lib/prometheus`
`for i in rules rules.d files_sd; do sudo mkdir -p /etc/prometheus/${i}; done`
![image](https://user-images.githubusercontent.com/88620315/141655112-ae4c4cae-8245-450f-9f76-c63344ee79aa.png)
3.	Download prometheus package
`curl -s https://api.github.com/repos/prometheus/prometheus/releases/latest | grep browser_download_url | grep linux-amd64 | cut -d '"' -f 4 | wget -qi -`
4.	Extract 
tar xvf prometheus*.tar.gz
5.	Masuk ke dalam folder hasil extract Prometheus
cd prometheus*/
6.	Pindahkan folder prometheus dan promtool ke usr/local/bin sudo mv prometheus promtool /usr/local/bin
![image](https://user-images.githubusercontent.com/88620315/141655264-f26f839c-da47-4107-b25e-574b21595261.png)
6.	Pindahkan Prometheus console configuration template ke /etc directory.
```
sudo mv prometheus.yml /etc/prometheus/prometheus.yml
sudo mv consoles console_libraries /etc/prometheus
```
![image](https://user-images.githubusercontent.com/88620315/141655294-fff7e3a5-4ac8-4004-8a5c-df1375d0b84f.png)
![image](https://user-images.githubusercontent.com/88620315/141655298-ea86b111-fd8b-41be-abf0-0f35591b9428.png)
7.	Add user prometheus 
```
sudo useradd -rs /bin/false prometheus
sudo chown -R prometheus: /etc/prometheus /var/lib/prometheus
```
8.	Buat service prometheus 
`sudo nano /etc/systemd/system/prometheus.service
`
 

>  [Unit]
>   Description=Prometheus 
>   After=network.target
> 
>   [Service]
>   User=prometheus   
>   Group=prometheus   
>   Type=simple
>   ExecStart=/usr/local/bin/prometheus \
>       --config.file /etc/prometheus/prometheus.yml \
>       --storage.tsdb.path /var/lib/prometheus/ \
>       --web.console.templates=/etc/prometheus/consoles \
>       --web.console.libraries=/etc/prometheus/console_libraries
> 
> [Install]
> WantedBy=multi-user.target
> 

9. Reload deamon 
`sudo systemctl daemon-reload`

10. Enable service 
`sudo systemctl enable prometheus`

11. Start prometheus 
`sudo systemctl start prometheus`

12. Cek status prometheus
`sudo systemctl status prometheus`
![image](https://user-images.githubusercontent.com/88620315/141655550-f58bcb4f-e415-4457-8335-ef95ddcf548a.png)

13. Akses ip server monitor dengan port 9090 
![image](https://user-images.githubusercontent.com/88620315/141655576-5bc89b76-51a9-4a1a-af74-aad930300f1c.png)
![image](https://user-images.githubusercontent.com/88620315/141655586-79af167c-3d95-4126-94f1-b260df716a2d.png)


# Install Grafana
1. download package grafana
`wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
`
2. install grafana
```
sudo apt-get update
sudo apt-get install grafana
```
3.	Enable grafana` systemctl enable grafana-server`
4.	Start grafana `systemctl start grafana-server`
5.	Kemudian cek status grafana `systemctl status grafana-server`
 
![image](https://user-images.githubusercontent.com/88620315/141655763-2673ffc2-58ab-4316-b46b-b2b07c02c7dd.png)

### Nonaktifkan signup grafana
6.	Edit config file grafana.ini` sudo nano /etc/grafana/grafana.ini`
7.	Pada bagian users ubah allow_sign_up -> false
8.	Kemudian set [auth.anonymous] ke enabled = false
9.	Restart service grafana `sudo systemctl restart grafana-server.service`
10.	Akses ip server monitor dengan port 3000
![image](https://user-images.githubusercontent.com/88620315/141656018-39f6bc66-ba80-4c5b-964e-fdc207c51d7e.png)

# Setup reverse proxy monitoring server
1.	Buat subdomain monitoring.nicky.onlinecamp.iddan arahkan ke ip server gateway.
 
![image](https://user-images.githubusercontent.com/88620315/141656045-115e0f19-f563-4dda-938b-650dca10f094.png)

2.	Login ke server gateway
3.	Tambahkan config untuk subdomain monitoring di folder conf.
4.	Restart nginx
5.	Buka browser akses monitoring.nicky.onlinecamp.id
 
![image](https://user-images.githubusercontent.com/88620315/141656048-e79ba8d3-52be-4fc9-bfa4-3f7c874072d4.png)
