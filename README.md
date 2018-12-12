# ansible-proxmox

## PVE IaaS proof of concept

Setup Proxmox VM menggunakan Ansible hanya dengan mendefinisikan VM pada sebuah file YAML dan juga menggunakan [proxmox_kvm](http://docs.ansible.com/ansible/latest/proxmox_kvm_module.html) module. 

## Prasyarat
### Umum

* Ansible 2.3 (proxmox_kvm module added)
* passwordless SSH access to target PVE node(s)

### Module Python
* proxmoxer
* requests

### Penggunaannya
* edit saja file `.yaml` sesuaikan dengan infra yang sudah ada.
* jalankan dengan menggunakan `ansible-playbook`

### Cloudinit

Saat ini Proxmox sudah mendukung cloud-init images, seperti halnya `Openstack`. Tinggal membuatkan template-nya dari image-nya yang ada di [image-openstack](https://docs.openstack.org/image-guide/obtain-images.html). dan juga module ini membutuhkan [update](https://github.com/morph027/ansible/blob/proxmox-kvm-cloud-init-settings/lib/ansible/modules/cloud/misc/proxmox_kvm.py) `proxmox_kvm`, Anda tinggal menaruhnya file ini di dalam folder `library` untuk menggunakannya.

