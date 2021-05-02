# Before you begin
KubeSpray is a **beast** to handle, but it's also the easiest way to deploy a production cluster of Kubernetes on bare metal. Always test in a staging environment that mirrors the production environment. The order of operations for deploying this entire stack **matters** and is **not automated**.

# Virtual Environment
The venv deploys the correct version of Ansible for KubeSpray. 

```
python3 -m venv ~/KubeSpray # you may need to install the python-venv package
source ~/KubeSpray/bin/activate
pip3 install wheel
pip3 install -r KubeSpray/requirements.txt
```

# Deploy to staging
```
cd KubeSpray
ansible-playbook -i ../KubeSprayInventory/staging/inventory.ini --user=ovh --become --become-user=root cluster.yml

```