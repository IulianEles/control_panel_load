# Load based node restart

This repository provides an add-on for configuring load based restarts for your Jelastic environmnent's application or load balancer nodes.

**Type of nodes this add-on can be applied to:**

- all application nodes
- all load balancer nodes

### What can it be used for?

Take automated action (reboot) when environment node is under load for prolonged periods of time.


### Installing

*Installing*
[![GET IT HOSTED](https://raw.githubusercontent.com/jelastic-jps/jpswiki/master/images/getithosted.png)](https://github.com/layershift/control_panel_load/blob/main/restart.jps)

To deploy this package to Jelastic Private Cloud, import [this JPS manifest](https://github.com/layershift/control_panel_load/blob/main/restart.jps) within your dashboard ([detailed instruction](https://docs.jelastic.com/environment-export-import#import)).

For more information on what Jelastic add-on is and how to apply it, follow the [Jelastic Add-ons](https://github.com/jelastic-jps/jpswiki/wiki/Jelastic-Addons) reference.

*You can install the add-on to any environment by selecting Add-ons for the desired node (load balancer or application server) and click on Install under the [add-on name].*

During installation you are asked to select the desired triggers for the node reboot:
![alt text](https://github.com/layershift/control_panel_load/blob/main/images/install.PNG)

* When: type of resource to monitor - CPU, Memory or Cloudlet usage
* Is higher than (%): percentage of load for the trigger
* For at least (min): duration of persistent load before activating the trigger

Once the add-on is installed, it will create a load alert for the trigger (*CPU_restart_alert*, *MEM_restart_alert* or *Cloudlet_restart_alert*). You can see and modify the conditions of the restart in the environment settings > Load alerts:

![alt text](https://github.com/layershift/control_panel_load/blob/main/images/alert.PNG)

***Note:** removing the related alert will stop the add-on from working.*
