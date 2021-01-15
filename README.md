az vm run-command invoke -g rajesh-demo-defalut-rg -n demo-vm --command-id RunShellScript --scripts ' wget  -O Dynatrace-ActiveGate-Linux-x86-1.207.193.sh "https://jrw92289.live.dynatrace.com/api/v1/deployment/installer/gateway/unix/latest?arch=x86&flavor=default" --header="Authorization: Api-Token $1" && sudo /bin/sh Dynatrace-ActiveGate-Linux-x86-1.207.193.sh' --parameters $MY_MESSAGE
#
