# Network Troubleshooting (Any Issues)

If any network issue occurs, follow the below troubleshooting steps:

1. **Check the destination server status**
   - Verify whether the server is **Up or Down**

2. **Check the connectivity from source server to destination server**
   - Example: `ping <IP>` or `telnet <IP> <port>` or `curl <URL>`

3. **Check the application status on the node**
   - Verify whether the application/service is running

4. **Check the application port listening status**
   - Example: `netstat -tulnp`, `ss -tulnp`, `lsof -i:<port>`

5. **Check connectivity within the same node**
   - Internal testing to validate service response

6. **Verify application logs**
   - Logs location: `/var/log/`
   - Example: `tail -f /var/log/<app>.log`
  
# Basic Information for Troubleshooting

### Source & Destination Details

| Parameter | Value |
|-----------|--------|
| **Source IP** | 172.17.0.3 |
| **Destination IP** | 172.17.0.2 |
| **Destination Port** | 8080 |
| **Application Name** | python |
| **Source IP:** | 172.17.0.3 |
| **Destination IP:** | 172.17.0.2 |
| **Destination port** | 6379 |
| **Application Name** | redis |

---

# Network Troubleshooting – All Commands Output (Without Issues)

## 1. Check the Destination Server Status (Up or Down?)

### Commands
```bash
hostname -i
ping -c2 172.17.0.2
```
#### Expected Output (Without Issue Example)
### Ping Output Example

```bash
ubuntu@SRINIVASARAO:~$ ping -c2 127.0.1.1
PING 127.0.1.1 (127.0.1.1) 56(84) bytes of data.
64 bytes from 127.0.1.1: icmp_seq=1 ttl=64 time=0.118 ms
64 bytes from 127.0.1.1: icmp_seq=2 ttl=64 time=0.033 ms

--- 127.0.1.1 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1046ms
rtt min/avg/max/mdev = 0.033/0.075/0.118/0.042 ms
```
## 2. Check the Connectivity from Source Server to Destination Server

### Commands
```bash
hostname -i
telnet telnet 127.0.1.1 8080
curl -av 127.0.1.1:8080
```
#### Expected Output 
```bash
ubuntu@SRINIVASARAO:~$ telnet 127.0.1.1 8080
Trying 127.0.1.1...
Connected to 127.0.1.1.
Escape character is '^]'.
Connection closed by foreign host.
ubuntu@SRINIVASARAO:~$
```
#### Expected Output 
```bash
ubuntu@SRINIVASARAO:~$ curl -av 127.0.1.1:8080
*   Trying 127.0.1.1:8080...
* Connected to 127.0.1.1 (127.0.1.1) port 8080
> GET / HTTP/1.1
> Host: 127.0.1.1:8080
> User-Agent: curl/8.5.0
> Accept: */*
>
< HTTP/1.1 403 Forbidden
< Server: Jetty(12.0.25)
< Date: Mon, 24 Nov 2025 12:57:00 GMT
< Vary: Accept-Encoding
< X-Content-Type-Options: nosniff
< Set-Cookie: JSESSIONID.be51a06d=node0tpgzhja6msjyblsnsmpqr4b0.node0; Path=/; HttpOnly; SameSite=Lax
< Expires: Thu, 01 Jan 1970 00:00:00 GMT
< Content-Type: text/html;charset=utf-8
< X-Hudson: 1.395
< X-Jenkins: 2.528.1
< X-Jenkins-Session: 192d9f68
< Transfer-Encoding: chunked
<
<html><head><meta http-equiv='refresh' content='1;url=/login?from=%2F'/><script id='redirect' data-redirect-url='/login?from=%2F' src='/static/192d9f68/scripts/redirect.js'></script></head><body style='background-color:white; color:white;'>
Authentication required
<!--
-->

* Connection #0 to host 127.0.1.1 left intact
</body></html>                                                                                                                                                                                                                                                                              ubuntu@SRINIVASARAO:~$
```
## 3. Check the Application Status on Node (where application is running)

### Commands
```bash
hostname -i
ps -ef | grep jenkins
systemctl status jenkisn
```
#### Expected Output 
```bash
ubuntu@SRINIVASARAO:~$ ps -ef | grep jenkins
jenkins      167       1  0 06:55 ?        00:01:23 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/java/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080
ubuntu     94949   57664  0 12:59 pts/2    00:00:00 grep --color=auto jenkins
ubuntu@SRINIVASARAO:~$ systemctl status jenkins
● jenkins.service - Jenkins Continuous Integration Server
     Loaded: loaded (/usr/lib/systemd/system/jenkins.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-11-24 06:24:34 UTC; 6h ago
   Main PID: 167 (java)
      Tasks: 60 (limit: 9312)
     Memory: 755.5M ()
     CGroup: /system.slice/jenkins.service
             └─167 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/java/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080

Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at hudson.model.UpdateSite.updateDirectlyNow(UpdateSite.java:235)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at hudson.PluginManager.checkUpdatesServer(PluginManager.java:2177)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at hudson.util.Retrier.start(Retrier.java:62)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at hudson.PluginManager.doCheckUpdatesServer(PluginManager.java:2148)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at jenkins.DailyCheck.execute(DailyCheck.java:93)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at hudson.model.AsyncPeriodicWork.lambda$doRun$0(AsyncPeriodicWork.java:110)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]:         at java.base/java.lang.Thread.run(Thread.java:840)
Nov 24 06:24:35 SRINIVASARAO jenkins[167]: 2025-11-24 06:24:35.400+0000 [id=73]        INFO        hudson.util.Retrier#start: Calling the listener of the a>
Nov 24 06:24:35 SRINIVASARAO jenkins[167]: 2025-11-24 06:24:35.402+0000 [id=73]        INFO        hudson.util.Retrier#start: Attempted the action check up>
Nov 24 06:24:35 SRINIVASARAO jenkins[167]: 2025-11-24 06:24:35.403+0000 [id=73]        SEVERE        hudson.PluginManager#doCheckUpdatesServer: Error check>
lines 1-19/19 (END)
```

## 4. Check the Application Port Listening Status on Node

### Commands
```bash
hostname -i
netstat -ntplu
```
```bash
ubuntu@SRINIVASARAO:~$ netstat -ntplu
(No info could be read for "-p": geteuid()=1000 but you should be root.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 127.0.0.1:39323         0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      -
tcp        0      0 10.255.255.254:53       0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:32783         0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -
tcp6       0      0 :::8080                 :::*                    LISTEN      -
udp        0      0 127.0.0.54:53           0.0.0.0:*                           -
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -
udp        0      0 10.255.255.254:53       0.0.0.0:*                           -
udp        0      0 127.0.0.1:323           0.0.0.0:*                           -
udp6       0      0 ::1:323                 :::*                                -
```

## 6. Finally verify the application logs in /var/log directory

### Commands
```bash
hostname -i
tail -5 /var/log/webapp-color.log
tail -5 /var/log/redis/redis-server.log
```









 



