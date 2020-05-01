# DDOS-Deflate
DDOS (Distributed Denial of Service) is a type of DOS (Denial of Service) attack in which an online service is made unavailable to its intended users. This is a frequently encountered attack due to availability of various tools online that are made to target a wide variety of important resources.  These tools are easy to use and are freely available on the internet in a simple google search. These tools make UDP, TCP or HTTP requests to the victim server.

<H2>Types of DDOS attacks:</h2> 

1) Application Layer DDOS attack
2) Protocol DDOS attack
3) Volume based DDOS attack

<b>Application Layer DDOS attack:</b> Application Layer DDOS attack is a type of DDOS attack which targets the application layer of OSI model. The size of these attacks are measured in requests per second (RPS).</br></br>
<b>Protocol DDOS attack:</b> Protocol DDOS attack targets server resources rather than bandwidth.</br></br>
<b>Volume based DDOS attack:</b> Volume based DDOS attack uses a variety of different techniques to saturate bandwidth of the attacked site, so other visitors can access it.  It eventually leads the server to crash.</br></br>

<b>There are three ways to defend against DDOS:</b></br>
1) Attack Prevention and Preemption: It is done before the attack.
2) Attack Detection and Filtering: It is done during the attack.
3) Attack Source: It can be done during and after the attack.

<h2>DDOS Deflate</h2>

DDOS Deflate is a lightweight bash shell script designed to block DOS attacks. It does not fully protect against large DDOS attacks, but it is helpful. It uses netstat command to track and monitor all the IP addresses making connections to the server. Whenever it detects the number of connections from a single node exceeding certain pretest limits which are defined in the configuration file, the script will automatically block that IP address through IP tables or APF according to the configuration. We can use the command below to list IP address connected to the server along with their total number of connections.
<br />```netstat -ntu | awk ‘{print $5}’ | cut -d: -f1 | sort | uniq -c | sort -n```<br />

<h1>DDOS Deflate Installation</h1>

<br />```cd /usr/local/src/```<br />
```wget http://www.inetbase.com/scripts/ddos/install.sh```<br />
```chmod 0700 install.sh```<br />
```./install.sh```<br />
<b>Edit configuration file</b><br />
```vi /usr/local/ddos/ddos.conf```<br />
<h2>Start DDOS Deflate</h2><br />
```/usr/local/ddos/ddos.sh -c```<br />
<h2>Unistall DDOS Deflate</h2><br />
```wget http://www.inetbase.com/scripts/ddos/uninstall.ddos```<br />
```chmod 0700 uninstall.ddos```<br />
```./uninstall.ddos```<br />
<h2>Features of DDOS Deflate</h2><br />
1) Whitelist IP addresses, via /usr/local/ddos/ignore.ip.list.<br />
2) Simple configuration file /usr/local/ddos/ddos.conf<br />
3) IP addresses are automatically unblocked after a preconfigured time limit.<br />
4) Script can run at a chosen frequency via the configuration file.<br />
5) Receive email alerts when IP addresses are blocked.<br />
6) Support APF, CSF and iptables.<br />
7) Helps to reduce the amount of processes opened by attackers using tcpkill.<br />
<b>Options of ddos deflate</b>To show the help screen<br />
```# ddos –help```<br />
<b>Create cron job to run the script regularly</b><br />
```# ddos –cron```<br />
<b>Display whitelisted IP addresses</b>
```#ddos -I | –ignore-list```<br />
<b>Display currently banned IP addresses.</b><br />
```# ddos -b | –bans-list```<br />
<b>To initialize a daemon to monitor connections.</b><br />
 ```# ddos -d | –start:```<br />
 <b>To Stop the daemon.</b><br />
 ```# ddos -s | –stop```<br />
 <b>To show status of daemon and pid currently running.</b><br />
 ```# ddos -t | –status```<br />
  <b>TTo display active connections to the server.</b><br />
 ```# ddos -v | –view```<br />
 <b>To block all IP addresses making more than N connections.</b><br />
 ```# ddos -k | –kill:```<br />




