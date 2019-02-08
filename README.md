# kubernetes

You will require ubuntu 16.04 VM instance for this.

once you launc the instance.  run below commands.

On master .

#copy the master shell script in installation directory . Change the IP in script with your internal IP

chmod a+x install-master.sh 

./kube-master.sh 

you will get a join command like below . note down that command

kubeadm join 10.142.0.9:6443 --token 2nlwag.w317esgnxnw8txvo --discovery-token-ca-cert-hash sha256:70425ed23c468329ad2bc68459831db2f913bce713ada3c7226840752e3514bf


cp /etc/kubernetes/admin.conf /root/
export KUBECONFIG=/root/admin.conf



Login to slave node

#copy the slave shell script.
chmod a+x install-node.sh

./install-node.sh

Run below join command

kubeadm join 10.142.0.9:6443 --token 2nlwag.w317esgnxnw8txvo --discovery-token-ca-cert-hash sha256:70425ed23c468329ad2bc68459831db2f913bce713ada3c7226840752e3514bf







