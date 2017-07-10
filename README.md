### Kubernetes on Tumbleweed

Deploy a fully working kubernetes (v1.7) cluster on openSUSE Tumbleweed with
Ansible.  

#### Configuration  
For instructions on how to configure this deployment you can read the
[instructions documentation](docs/INSTRUCTIONS.md).

#### Architecture
For a detailed overview of the platform you can read the [architecture
documentation](docs/ARCHITECURE.md).

#### Ansible 2.3

If your OS doesn't contain Ansible 2.3, the easiest way to install it is to
follow these instructions:

Install python virtualenv.
```
zyp in -y python-virtualenv
Loading repository data...
Reading installed packages...
Resolving package dependencies...
The following NEW package is going to be installed:
  python-virtualenv
...
```

Create a new virtualenv in `.venv` source the `activate` script.
And make sure you're using the right `pip` before installing Ansible.
This will require some lib\*-devel packages to be installed on your system.
```
virtualenv .venv
New python executable in .venv/bin/python
Installing setuptools, pip, wheel...done.

source .venv/bin/activate
which pip
/home/user/k8s-tumbleweed/.venv/bin/pip
```

```
pip install ansible
Collecting ansible
  Using cached ansible-2.3.1.0.tar.gz
...
```

Create a symlink to the ansible bin from the virtual environment.
```
ln -s .venv/bin/ansible-playbook ansible-playbook
```

Now you can use ansible 2.3 from your symlink.
```
./ansible-playbook site.yaml --inventory-file=inventory.yaml
```
