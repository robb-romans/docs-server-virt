.. _why-is-datastore-overhead-required:


===================================
Why is datastore overhead required?
===================================


We require datastore overhead for the following reasons:

* Some files and features (for example, snapshots, including snapshots
  made automatically by VM recovery) might consume datastore space rapidly
  and without your awareness.

* If a datastore runs out of free space, it can cause downtime.
  A VM’s performance can be negatively impacted when the datastore
  is critically low on space.

* Certain VMware features, such as snapshots, might no longer function
  without sufficient datastore space.

* Powered-on VMs have a vSwap file equivalent in size to the amount of
  vRAM assigned to the VM. For example, a VM with 128 GB of RAM has a
  128 GB vSwap file. vSwap files only exist for VMs that are powered on.
  Powering on a VM or increasing the amount of vRAM in your VM consumes
  additional space on the datastore.

* A VM might not power on due to insufficient space on the datastore.

* All VM log files are stored within the VM container folder on the
  datastore. A typical log file is a few MB in size; however,
  log files can grow to a few GB in size depending on VM activity and
  DRS migrations.

* VM Recovery requires additional space because the VM takes snapshots
  frequently, potentially on multiple VMs at the same time.
