# infinispan-cluster-installation


Download the infinispan and unzip

     wget https://downloads.jboss.org/infinispan/13.0.10.Final/infinispan-server-13.0.10.Final.zip
     unzip -q infinispan-server-13.0.10.Final.zip
     mv infinispan-server-13.0.10.Final /var/is-13
     cd /var/is-13

Copy cluster.xml and made necessary changes on the file.

Possibly changes


with server ip addresses


     initial_hosts="${jgroups.tcpping.initial_hosts:10.0.0.1[7800],10.0.0.2[7800],10.0.0.3[7800],10.0.0.4[7800]}"
     

with cluster and node name


     <transport cluster="${infinispan.cluster.name:myCluster}" stack="prod"  node-name="${infinispan.node.name:node-1}"/>
     
     
on the /var/is-13 directory run the command at see it running 


     bin/server.sh -c cluster.xml


Try same procedure for each node.
