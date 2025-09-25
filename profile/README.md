# Welcome to CSC478-WCU! 
## This is a organization to hold our group projects for CSC478 - Cloud Computing 2!


## Group Members: 
 - Edwin Biswas
 - Alex Cooper
 - Tyler Geiger
 - Kadin Matotek 
 
 

## Repositories:

 - [Terraform-Provider-Cloudlab](https://github.com/csc478-wcu/terraform-provider-cloudlab)
 - [PortalCTL](https://github.com/csc478-wcu/portalctl)
   - A GO CLI for interacting with the cloudlab [XMLRPC](https://xmlrpc.com/) API. 
   - Allows for `creating` `modifying` `terminating` and `rebooting` experiments from the command line.
   - Defines `portal` interface for interacting with cloudlab over [XMLRPC](https://xmlrpc.com/) which is used in our [terraform provider](https://github.com/csc478-wcu/terraform-provider-cloudlab)
 - [CC2-Cluster](https://github.com/csc478-wcu/cc2-cluster)
   - CI/CD Pipeline (Ansible + Terraform) for initializing nodes & helm charts
   - Helm Charts
   ```mermaid
   flowchart LR
    A[Workflow Dispatch<br/>GitHub Actions Trigger] --> B[Terraform Apply<br/>Provision CloudLab nodes]
    B --> C[Terraform Outputs<br/>nodes_json, ssh_user, IPs]
    C --> D[Ansible SSH<br/>Bootstrap Cluster]
    D --> E[Set up kubeadm<br/>Init + Join Nodes]
    E --> F[Deploy MetalLB<br/>Configure IP Pools]
    F --> G[Deploy Helm Charts<br/>Ingress-NGINX, ExternalDNS, Apps]
    ```
