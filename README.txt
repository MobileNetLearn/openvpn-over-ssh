iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -j SNAT --to-source <SERVER-IP>

cat /etc/resolv.conf
sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'

ssh root@<SERVER-IP> -L 1194:localhost:443 -N
sudo openvpn --config client1.ovpn
