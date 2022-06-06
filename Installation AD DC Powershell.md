1.	Run the cmd.exe as administrator and type powershell then press **ENTER**.
2.	Set the IP Address of the server.

New-NetIPAddress -InterfaceAlias "Alias" -IPAddress "xxx.xxx.x.x" -PrefixLength 24 -DefaultGateway "xxx.xxx.x.x"

![netipaddress.png](https://github.com/toytarugs/active-directory/blob/main/img/netipaddress.png?raw=true)

2. Configure the DNS Address of the server.

Set-DnsClientServerAddress -InterfaceAlias "Alias" -ServerAddresses "xxx.xxx.x.x"

![dnsclientaddress.png](https://github.com/toytarugs/active-directory/blob/main/img/dnsclientaddress.png?raw=true)

3. Install windows feature for ADDS services.

Add-WindowsFeature AD-Domain-Services to install ADDS

![add-adds.png](https://github.com/toytarugs/active-directory/blob/main/img/add-adds.png?raw=true)

4. Create a new Active Directory forest, install DNS and promote the server to a DC (Domain Controller).

Install-ADDSForest -DomainName (yourdomainname) -InstallDns

	Type DSRM password twice and Enter to save the password.
	Type A and Enter to configure the server as a domain controller and install DNS.

![install-addsforest.png](https://github.com/toytarugs/active-directory/blob/main/img/install-addsforest.png?raw=true)

![install-addsforests.png](https://github.com/toytarugs/active-directory/blob/main/img/install-addsforests.png?raw=true)

	Wait until the installation done and reboot the server.
	Note: All other parameters are set as default.

