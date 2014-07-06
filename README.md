# logstash_kibana


Testing deployment of logstash, kibana, and elasticsearch using rabbitmq for communications. 

## To deploy
1. vagrant up
2. ansible-playbook -i hosts --private-key=~/.vagrant.d/insecure_private_key site.yml 
