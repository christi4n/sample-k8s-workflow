# Sample K8s deployment with GoCD

## Required authorizations

Clone the following repository: https://github.com/christi4n/amaris-ocsin.git

   kubectl apply -f k8s/gocd/secrets-for-gocd-agent.yml -n gocd
   kubectl apply -f k8s/gocd/agent-role.yml

## Expose the service and add a domain with Ingress

   kubectl expose deployment  bulletin-board-deployment --type=LoadBalancer --port=8080 --target-port=8080 --namespace=gocd

Add Ingress:

   kubectl apply -f bulletin-board-service.yml

The board is accessible with the following url: http://bulletin-board.info:8080/