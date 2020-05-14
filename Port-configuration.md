## Port configuration


### AWS

* Add the rule to the security group using one of the following commands :   
   
  1. [authorize-security-group-ingress](https://docs.aws.amazon.com/cli/latest/reference/ec2/authorize-security-group-ingress.html) (AWS CLI)
  
     ```
     aws ec2 authorize-security-group-ingress --group-id security_group_id --protocol tcp --port 22 --cidr cidr_ip_range
     ```
  2. Grant-EC2SecurityGroupIngress (AWS Tools for Windows PowerShell)

      The Grant-EC2SecurityGroupIngress command needs an IpPermission parameter, which describes the protocol, **port range**, and IP address range to be used for the security group rule. The following command creates the IpPermission parameter:

      ```
      PS C:\> $ip1 = @{ IpProtocol="tcp"; FromPort="22"; ToPort="22"; IpRanges="cidr_ip_range" }
      ```
      ```
      PS C:\> Grant-EC2SecurityGroupIngress -GroupId security_group_id -IpPermission @($ip1)
      ```
      [Authorizing inbound traffic for your Linux instances](https://docs.aws.amazon.com/zh_tw/AWSEC2/latest/UserGuide/authorizing-access-to-an-instance.html)


### GCP

   **Configure specified port 32440-32440**

* To show all firewall rules for all networks in your project:

   Go to the Firewall rules page in the Google Cloud Console.
   [Go to the Firewall rules page](https://console.cloud.google.com/projectselector2/networking/firewalls/list?_ga=2.261730702.2017250339.1589442185-1859086525.1588041842&_gac=1.82358628.1588216859.Cj0KCQjwy6T1BRDXARIsAIqCTXqCo0_oQvb6HcxxyzQHkDab6BgjD39oKjb6ooePCO-W7_MetqwK1MAaAsuGEALw_wcB&supportedpurview=project)

* To show firewall rules in a particular network:
   1. Go to the VPC networks page in the Google Cloud Console.
      [Go to the VPC networks page](https://console.cloud.google.com/projectselector/networking/networks/list?_ga=2.26188222.2017250339.1589442185-1859086525.1588041842&_gac=1.60104159.1588216859.Cj0KCQjwy6T1BRDXARIsAIqCTXqCo0_oQvb6HcxxyzQHkDab6BgjD39oKjb6ooePCO-W7_MetqwK1MAaAsuGEALw_wcB&supportedpurview=project)
   2. Click the Name of a VPC network to go to its details page.
   3. On the details page for the network, click the Firewall rules tab.

      * VPC Network → Firewall rules → Create Firewall rule   
      * Protocols and ports → Specified protocols and ports → TCP `32440-32449` 
     
        <img src= "https://github.com/poseidon-network/qlauncher-linux/blob/master/image/GCP%20VPC%20Network.png" width="50%" height="50%" alt="VCP Network" /><img src= "https://github.com/poseidon-network/qlauncher-linux/blob/master/image/GCP%20Ports.png?raw=true" width="50%" height="50%" alt="tcp 32440-32449" />  
           
           [Using firewall rules](https://cloud.google.com/vpc/docs/using-firewalls)
