az vm run-command invoke -g rajesh-demo-defalut-rg -n demo-vm --command-id RunShellScript --scripts ' wget  -O Dynatrace-ActiveGate-Linux-x86-1.207.193.sh "https://jrw92289.live.dynatrace.com/api/v1/deployment/installer/gateway/unix/latest?arch=x86&flavor=default" --header="Authorization: Api-Token $1" && sudo /bin/sh Dynatrace-ActiveGate-Linux-x86-1.207.193.sh' --parameters $MY_MESSAGE
#



how to save dashboard shell script 
working script

# array=( 'Kubernetes-cluster-overview-api-test2' 'Kubernetes-cluster-overview-api-test-3' 'Kubernetes-cluster-overview-api-test' ) 
# for u in "${array[@]}"
# do
    
#     dashboardid=$(curl -X GET https://wfu44453.live.dynatrace.com/api/config/v1/dashboards/ -H 'Authorization: Api-token '"$token"'' | jq '.dashboards[] | select (.name== '\"$u\"') | .id' | sed 's/"//g')
#     echo    "my :$dashboardid"
#     curl -X GET https://wfu44453.live.dynatrace.com/api/config/v1/dashboards/"$dashboardid" -H 'Authorization: Api-token '"$token"'' > $u.json
# done



restoring bit not working need

# restore testing now 
array=( 'Kubernetes-cluster-overview-api-test2' 'Kubernetes-cluster-overview-api-test-3' 'Kubernetes-cluster-overview-api-test' ) 
for u in "${array[@]}"
do
    dashboardid=$(curl -X GET https://wfu44453.live.dynatrace.com/api/config/v1/dashboards/ -H 'Authorization: Api-token '"$token"'' | jq '.dashboards[] | select (.name== '\"$u\"') | .id' | sed 's/"//g')
    echo    "my :$dashboardid"
    restorejson=$(cat $u.json)
    echo "my resotrefile name =>  $u.json"
    cat $u.json | xargs echo -e| curl -X PUT --data-binary @- https://wfu44453.live.dynatrace.com/api/config/v1/dashboards/"$dashboardid" -H 'Authorization: Api-token '"$token"'' -H 'Content-Type:application/json' 
                                                                                                                                    
done
