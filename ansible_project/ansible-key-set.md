# Simpan Kunci Privat
1. Pertama copas key untuk akses kedalam server yg akan dimanage "***nano ~/.ssh/<nama-key.pem>***"
2. Kemudian beri Permission ke key "***chmod 600 ~/.ssh/<nama-key.pem>***"
3. Configurasi SSH Agent
   '''
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/<nama-key.pem>
   '''
