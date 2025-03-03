---
description: >-
  A quick reminder of one of the ways of how to dump memory of a VM running on
  VirtualBox in Linux environment.
---

# Dump Virtual Box Memory

## Enable Debug Mode

{% tabs %}
{% tab title="linux host" %}
```bash
mantvydas@~: virtualbox --startvm 'yourVMName or VM UUID' --dbg
```
{% endtab %}
{% endtabs %}

## Dump VM Memory

Launch the VirtualBox debug console by navigating to "Debug" menu an select "Command Line":

![](../.gitbook/assets/vbox-menu.png)

Once you select "Command Line", you will be presented with a console that looks like this:

![memory dump will be a raw file dumped to /home/youruser directory](../.gitbook/assets/vbox-debug.png)

To create a memory dump, issue the below command \(also highlighted in the above graphic\):

{% tabs %}
{% tab title="VM@virtualbox" %}
```text
VBoxDbg> .pgmphystofile 'w7-nc-shell.bin'
```
{% endtab %}
{% endtabs %}

## Persistence

If you want the debug options to be always available, you can:

* export `VBOX_GUI_DBG_ENABLED=true` before launching the VM or
* put export `VBOX_GUI_DBG_ENABLED=true` in your `.bashrc` or `/etc/environment` 

