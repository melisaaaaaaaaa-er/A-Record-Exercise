# A-Record Exercise

![1](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/21a5158b-61a1-4183-be9b-e91b805748f0)
On Client-1, perform ping and nslookup on “mainframe”. Notice how it doesn't work.

When performing these commands, a computer will first check its local DNS cache to see if it has a record for the name being looked up. Computers store such records here to prevent having to reach out to DNS servers each time and avoid generating additional traffic on the network.

If there is no record in the DNS cache, the computer will then check its host file (C:\Windows\system23\drivers\etc\hosts) to see if a record of the relevant mapping exists. This file is typically empty by default.

If both the DNS cache and host file do not hold the appropriate record, the computer will finally reach out to the DNS server on the network to make the resolution.

If none of these three have the needed record, the resolution fails.

#
![2](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/be18b518-614e-4ad2-8117-1c3c69571747)

![3](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/ba7b1582-a2e0-4633-967f-6064827b1cd0)
On DC-1, go to Tools → DNS → DC-1 → Forward Lookup Zone → right-click -your domain- → New Host (A or AAAA)...

#
![4](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/d7c9e497-e6c3-4916-af11-393baa7675a3)
Input “mainframe” in the Name category, and the private IP address of DC-1 in the IP address area. Click “Add Host”.

#
![5](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/d709e800-3e00-4cba-ad1f-d8f8323f29ca)

![6](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/fc704775-e7ed-4e7c-8fb2-74fe8b61f566)
An A Record (a record mapping a name to an IPv4 address) has been created for “mainframe” tying it to DC-1.

#
![7](https://github.com/melisa-er/A-Record-Exercise/assets/157723219/c3bc9e1b-6bbc-4604-83e5-c5913428b62c)

Do a ping and nslookup for “mainframe” again. It will work now that there is a record for it in the DNS server.
