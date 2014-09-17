ansible-playbooks
=================

Ansible playbooks

## Matlab

This playbooks goes through the steps of a Matlab installation from an
ISO image. The ISO image could be made visible in two ways:
 * By providing an URL where the ISO image could be taken from
 * By providing a Cinder Volume ID containing the ISO image. 

The license activation type is Network Concurrent Lincese.

The playbook makes use of the ``roles/openstack/tasks/cinder.yml``
task to attach a Cinder Volume containing the Matlab ISO image (in
this case the variable ``download_iso`` should be set to ``false``).

How to use the playbook:

    $ ansible-playbook -i <inventory_file> matlab.yml vm_id=<>
    volume_id=<>

As the ``openstack/cinder`` task uses the nova CLI, it is required
that the ``python-novaclient`` package is installed and the
OS_USERNAME, OS_PASSWORD, OS_TENANT_IS, OS_AUTH_URL environmental
variable defined.

## Matlab MCR

This playbook install only a Matlab MCR environment. This allows to
run Matlab compiled scripts without the need of a license activation.

How to use the playbook:
    $ ansible-playbook -i <inventoy_file> matlab-mcr.yml

## USZ

This is a playbook created for the UniSpital usecase. It complements
the ``gridengine`` playbook available in elasticluster.

The playbook simply creates few additional mount point on the cluster
frontend and export them to the other nodes of the cluster.

## Benchmark mm.ibf.uzh

This playbook has been created for a usecase from the Institute of
Banking and Finance at the University of Zurich.

The playbook deploys igraph for C++, python and R.
By using the ``install_python`` ``install_R`` ``install_cpp``
variables, it is possible to deploy any of them.

