# 1. Monitor System Resources
top
htop

# 2. Check Disk Usage
df -h
du -sh *

# 3. View Service Logs
sudo journalctl -u nginx.service -f

# 4. Check Who Uses a Port
sudo lsof -i :8080

# 5. Network Diagnostics
ss -tulnp

# 6. Compress & Extract Files
tar -czvf backup.tar.gz /etc/nginx
tar -xzvf backup.tar.gz

# 7. Text Search & Filter
grep "ERROR" /var/log/syslog
awk '{print $1, $2, $5}' access.log
sed -i 's/old/new/g' file.txt

# 8. Manage Services
sudo systemctl restart docker
sudo systemctl enable nginx

# 9. Manage Processes
ps aux | grep java
sudo kill -9 <PID>

# 10. Find Files
find /var/log -type f -name "*.log" -size +10M

# Bonus — Combine Like a Pro
ps aux | grep nginx | awk '{print $2}' | xargs sudo kill -9
