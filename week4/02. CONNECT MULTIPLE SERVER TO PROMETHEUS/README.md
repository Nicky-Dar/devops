Connect multiple server to prometheus
Install Node Exporter pada server yang akan dimonitoring
1.	Login server monitoring dan target
2.	Install node exporter
 
![image](https://user-images.githubusercontent.com/88620315/141675403-480eefaa-6cc6-48df-9f2d-5755b5763b06.png)

3.	Konfigurasikan file prometheus.yml 
sudo nano /etc/prometheus/prometheus.yml
```
global:
  scrape_interval: 10s

scrape_configs:
   - job_name: 'prometheus-metrics'
     scrape_interval: 10s
     static_configs:
       - targets: ['localhost:9100']
   - job_name: 'node_exporter_metrics'
     scrape_interval: 5s
     static_configs:
       - targets: ['localhost:9100', …] #Ip address target
```

4.	Restart prometheus service 
sudo systemctl restart prometheus.service
5.	Masuk ke server promtheus di port 9090
6.	Pada bagian graph cari metric yang ingin ditampilkan
7.	Execute
 
Menampilkan cpu dan memory process menggunakan grafana
1.	Login ke server monitoring grafana
2.	Tambahkan data source dari prometheus
 
![image](https://user-images.githubusercontent.com/88620315/141675481-b936757c-1f2d-443f-92b1-eb4b8e7bb761.png)

3.	Masukkan URL server Prometheus .
![image](https://user-images.githubusercontent.com/88620315/141675490-c014443d-6591-497f-aa48-7e71a9b5fff0.png)

4.	Save & test. 
 
![image](https://user-images.githubusercontent.com/88620315/141675502-70242359-365d-4a6a-913b-890e3bb9b318.png)

Buat panel untuk cpu usage
1.	Add new panel
2.	Pada bagian Query, masukan rumus berikut untuk menampilkan CPU usage
100 - (avg by (instance) (irate(node_cpu_seconds_total{job="node",mode="idle"}[5m])) * 100)
3.	Beri nama pada panel kemudian simpan.
  
![image](https://user-images.githubusercontent.com/88620315/141675511-cd30b43e-2030-4e11-881f-1b2379d23da5.png)

Buat panel untuk memory usage
1.	Add new panel
2.	Pada bagian Query, set Metric Browser node_memory_Active_bytes
3.	Di bagian panel cari standart options. Pilin Unit Data rate ->bytes(SI)
  
![image](https://user-images.githubusercontent.com/88620315/141675527-74c836f4-e036-4b08-8b3d-955f26df104f.png)

Buat panel untuk networking
1.	Add new panel kemudian edit.
2.	Masukan function rate() 
rate(node_network_transmit_bytes_total[5m]) * 8
 
![image](https://user-images.githubusercontent.com/88620315/141675533-5e127b27-d46c-4418-a56f-566edf7eaf7e.png)

Buat panel untuk Storage
1.	Add new panel
2.	Pada bagian Query, cari dan set Metric Browser untuk menampilkan available storage node_filesystem_avail_bytes{mountpoint="/",fstype!="rootfs"}
3.	Tambahkan query lagi untuk menampilkan size storage node_filesystem_size_bytes{mountpoint="/",fstype!="rootfs"}
4.	Di bagian panel cari standart options. Pilin Unit bytes(SI)
5.	Pilih graph type Stat
 
![image](https://user-images.githubusercontent.com/88620315/141675536-dcdd896b-dd8f-4e31-b8ac-d2fe2bdb8baa.png)
