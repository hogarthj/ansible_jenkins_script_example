## A working jenkins_script example for an automated jenkins install

This is designed to complement my recent article on using jenkins_script
[here](https://www.hogarthuk.com/?q=node/16).

To make use of this you'll need a CentOS7 container or virtual machine
and a github account.

Add a hosts file with the target system in a 'jenkins' group and amend
group_vars/jenkins with the details of your github account.

Then just run the playbook:

```
ansible-playbook -i hosts site.yml
```

After a few minutes there will be a running jenkins instance parsing
through your github account for any repositories that have a Jenkinsfile
in their branch to run.

For a sample one for it to pick up clone
[test_scenario](https://github.com/hogarthj/test_scenario) which will
result in a binary that random (roughly 50/50) has a non-zero exit code.

This example requires gcc, make and openssl-devel on the jenkins server
to build the binary. These will be installed from the included site.yml




