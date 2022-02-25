# Deploy IBM Turbonomic Application Resource Management (ARM) using Ansible

[Turbonomic](https://www.turbonomic.com/) AI-powered Application Resource Management simultaneously optimizes performance, compliance, and cost in real time.  

This repository provides Ansible-way to deploy Turbonomic ARM on an existing OpenShift Cluster. 

### 1. Pre-requisites
Please ensure that the following pre-requisites are met before executing the ansible scripts to deploy CP4WAIOps.

1. You need an ansible-controller machine from which the scripts are executed. This could be your laptop or a dedicated linux machine. This can only be a Mac or Linux machine and NOT Windows.
2. Install Python 3.10+ on the ansible-controller. Check the version with 'python --version'.
3. Install Ansible 2.12+ on the ansible-controller.Check the version with 'ansible --version'.
4. Ensure that the Python used by Ansible matches with the Python version on the ansible-controller.
5. Setup OpenShift and ensure that it is reachable from ansible-controller.
6. Install 'oc' (OpenShift CLI) client on ansible-controller.
7. Login into OpenShift cluster using 'oc login' from the ansible-controller.
8. Install the kubernetes core collection for Ansible by running 'ansible-galaxy collection install kubernetes.core'.

**Notes**:
1. The scripts are tested with Python 3.10.1 and Ansible 2.12.1 on MacOS.
2. The scripts are work-in-progress and updated frequently.
3. The script is meant for setup of sandbox environment only on IBM ROKS (OpenShift on IBM Cloud) and not for production.


### 2. Run the scripts to deploy Turbonomic ARM

You need to clone the repository on ansible-controller machine. 

Run the following command to run the ansible script, which deploys CP4WAIOps. 

```
ansible-playbook deploy-turbo.yml
```
It would take about 30 minutes for the installation to complete. Once the installation is completed, the URL to access the Turbonomic console is presented on the screen. Use them to access the console and checkout the features while going through [Turbonomic Documentation](https://docs.turbonomic.com/). 

### 3. Uninstall Turbonomic ARM

Run the following command to uninstall Turbonomic ARM that was installed in the previous step:
```
ansible-playbook uninstall-turbo.yml
```

After the shell script is executed completely, Turbonomic ARM is removed from the target OpenShift Cluster. 