# A-Record Exercise

<h3>Purpose</h3>

- Configure and test an A-Record on a Windows DNS Server.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/1.png"/>
On Client-1, perform ping and nslookup on “mainframe”. Notice how it doesn't work.

When performing these commands, a computer will first check its local DNS cache to see if it has a record for the name being looked up. Computers store such records here to prevent having to reach out to DNS servers each time and avoid generating additional traffic on the network.

If there is no record in the DNS cache, the computer will then check its host file (C:\Windows\system23\drivers\etc\hosts) to see if a record of the relevant mapping exists. This file is typically empty by default.

If both the DNS cache and host file do not hold the appropriate record, the computer will finally reach out to the DNS server on the network to make the resolution.

If none of these three have the needed record, the resolution fails.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/2.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/3.png"/>
On DC-1, go to Tools → DNS → DC-1 → Forward Lookup Zone → right-click -your domain- → New Host (A or AAAA)...

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/4.png"/>
Input “mainframe” in the Name category, and the private IP address of DC-1 in the IP address area. Click “Add Host”.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/5.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/6.png"/>
An A Record (a record mapping a name to an IPv4 address) has been created for “mainframe” tying it to DC-1.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/7.png"/>

Do a ping and nslookup for “mainframe” again. It will work now that there is a record for it in the DNS server.
