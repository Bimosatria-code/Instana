# Uninstall Instana Agent Airgapped

Untuk Uninstall dilinux RHEL

1. Jalankan command “**yum list installed | grep instana-agent**”

2. Kemudian jalankan command “**sudo yum remove <package_name>**”

3. Terakhir hapus repository installation “**rm -rf /opt/instana/agent**”
