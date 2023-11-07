# Install Instana Agent Airgapped

1. Download agent di “**[https://_](https://_/):<download-key>@packages.instana.io/agent/download”**

2. Setelah didownload copy file.rpm ke server

3. Jalankan “s**udo rpm -ivh <instana-agent.rpm>”**

4. Verification installation dengan jalankan “**systemctl status instana-agent”**

5. Masuk **/etc/systemd/system/instana-agent.service.d/**

6. Kemudian buat file **10-environment.conf** 

7. Dan isikan configurasi berikut

`**[Service]**

**Environment=INSTANA_KEY=<instana_agentkey>**

**Environment=INSTANA_HOST=<instana_endpoint>**

**Environment=INSTANA_PORT=<instana_endpoint_port>`**

8. Lalu jalankan “**sudo systemctl daemon-reload” dan “****sudo systemctl restart instana-agent”**

9. Setelah itu jalankan command berikut untuk membuat configuration-zone.yaml

```
INSTANA_ZONE="OracleServer" && \
cat <<EOF | sudo tee /opt/instana/agent/etc/instana/configuration-zone.yaml
# Hardware & Zone
com.instana.plugin.generic.hardware:
  enabled: true
  availability-zone: "${INSTANA_ZONE}"
EOF
```

10. Setelah itu jalankan command berikut untuk membuat configuration-host.yaml

```jsx
cat <<EOF | sudo tee /opt/instana/agent/etc/instana/configuration-zone.yaml
# Host
com.instana.plugin.host.tags:    
    - poc
    - crm
    - linux
EOF
```

11. Terakhir jalankan “**sudo systemctl restart instana-agent”**
