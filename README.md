# Load based node restart

This repository provides an add-on to restart Jelastic application or load balancers nodes if resource usage is high for a sustained period of time.

**Type of nodes this add-on can be applied to:**

- all application nodes
- all load balancer nodes

### What can it be used for?

Take automated action (reboot) when environment node is under load for prolonged periods of time.

### Why is it useful?

It can be used as a workaround to recover from abnormal conditions, such as an unidentified code malfunction.

### Installing

[![GET IT HOSTED](https://raw.githubusercontent.com/jelastic-jps/jpswiki/master/images/getithosted.png)](https://app.j.layershift.co.uk/?manifest=https://github.com/layershift/control_panel_load/blob/main/restart.jps)

*You can install the add-on to any environment by selecting Add-ons for the desired node (load balancer or application server) and click on Install under the Load based node restart.*

During installation you are asked to select the desired triggers for the node reboot:
![alt text](https://github.com/layershift/control_panel_load/blob/main/images/install.PNG)

* When: type of resource to monitor - CPU, Memory or Cloudlet usage
* Is higher than (%): percentage of load for the trigger
* For at least (minutes): duration of persistent load before activating the trigger

Once the add-on is installed, it will create a load alert for the trigger (*CPU_restart_alert*, *MEM_restart_alert* or *Cloudlet_restart_alert*). You can see and modify the conditions of the restart in the environment settings > Load alerts:

![alt text](https://github.com/layershift/control_panel_load/blob/main/images/alert.PNG)

All environment collaborators will receive an email notification each time the alert is triggered (and all nodes in the selected nodeGroup - e.g. all load balancer or application server nodes within the selected environment - will be restarted)

***Note:** removing the related alert will stop the add-on from working.*

### Custom actions

Before triggering the node group restart the add-on will execute, if it exists, ~/watchdog_before_restart.sh. Just open webSSH or login via SSH then edit and save ~/watchdog_before_restart.sh.

***Note:** chmod +x ~/watchdog_before_restart.sh*
