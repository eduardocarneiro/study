# Arquitetura de VPC's - Repositórios da Aula

## Repositórios Usados em Aula

Repositório Central do Curso - https://github.com/msfidelis/linuxtips-curso-containers-aws  

Repositório da Infraestrutura de VPC - https://github.com/msfidelis/linuxtips-curso-containers-vpc


---


## Day-0 - Arquitetura de VPC's
## Day-1 - ECS: Elastic Container Service

### Elastic Container Service - ECS Cluster
	create variables on variables.tf
		nodes_ami
		node_instance_type
		node_volume_size
		node_volume_type
	create variables value on terraform.tfvars
	create a security_group for nodes ECS on sg.tf file
	create a security_group_rule for nodes ECS on sg.tf file
	create the ecs cluster on ecs.tf

### Elastic Container Service - ECS Instance Nodes
	create a script userdata for nodes on templates/user-data.tpl
	create a aws_launch_template on file launch_template.tf
	create a autoscale_group on asg.tf
	create variables for cluster on variables.tf file
		cluster_on_demand_min_size
		cluster_on_demand_max_size
		cluster_on_demand_desired_size
		
### Elastic Container Service - Capacity Providers e Spots
	create a aws_ecs_capacity_provider on asg.tf
	create a aws_ecs_cluster_capacity_providers resource on ecs.tf file
	create variables for spot resource on variabels.tf
	create a new launch_template_spots.tf file
	create a new asg_spots.tf file
	
## Day-2 - ECS: Terraform Module, Services, Task Definitions e Tasks

### Elastic Container Service - Setup do Módulo do Service
	create a git repo to store the service
		create variables on variables.tf file
		service_name
		cluster_name
		vpc_id
		private_subnets
		service_port
		service_cpu
		service_memory
		service_listener

	create a git repo to store the app test
		create directory app
			create app/Dockerfile
		create terraform diretory
		create terraform/variables.tf
		create terraform/providers.tf
		create terraform/output.tf
		create terraform/main.tf
		create terraform/data.tf
		create terraform/backend.tf
		create the directory terraform/environment/dev
		create the terraform/environment/dev/backend.tfvars
		create the terraform/environment/dev/terraform.tfvars 
		
		
v		
## Day-3 - ECS: Autoscaling
## Day-4 - ECS: Fargate
## Day-5 - ECS: Pipeline com Github Actions
## Day-6 - ECS: Elastic File System
## Day-7 - ECS: Secret Manager e Parameter Store
## Day-8 - ECS: Exposição, Roteamento Avançado e Service Discovery
## Day-9 - ECS: Exposição e Networking - Service Connect
## Day-10 - ECS: OpenAPI e Exposição via API Gateway
## Day-11 - ECS: Blue/Green e Canary com CodeDeploy
## Day-12 - ECS: Projeto Final Multi-Region - Networking Multi-Region
## Day-13 - ECS: Projeto Final Multi-Region - Clusters e Computing Multi-Region
## Day-14 - ECS: Projeto Final Multi-Region - Roteamento Multi-Region e Toggles com AWS Global Accelerator
## Day-15 - ECS: Projeto Final Multi-Region - Workload Multi-Region - Deployment e Replicação de Dados
## Day-16 - ECS: Projeto Final Multi-Region - Roteamento de API's Multi-Region


