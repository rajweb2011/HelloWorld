# HelloWorld
az vm run-command invoke -g rajesh-demo-defalut-rg -n demo-vm  --command-id RunShellScript --scripts "sudo systemctl status nginx" | grep -ow "running"
