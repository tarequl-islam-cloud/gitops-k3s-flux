# Task 1: Cluster Setup and Application Deployment
Create a Kubernetes cluster with k3s on your local machine.
●​ Use FluxCD (GitOps tool) to bootstrap the Flux controller into the cluster, and configure it
to sync the cluster state from a GitHub repository.
●​ Set up SOPS with age for secret encryption in FluxCD.
●​ Deploy a bare-metal load balancer solution (e.g., MetalLB or OpenELB).
●​ Deploy ingress-nginx using Helm (chart version 4.11.7) via FluxCD:
○​ Configure Helm values to deploy the ingress-nginx controller as a LoadBalancer
service.
●​ Deploy the following workloads via FluxCD
○​ MySQL database. MySQL secrets (username & password) must be encrypted
with SOPS & age, and stored in GitHub.
○​ Deploy WordPress​
Expected Result: After deployment, WordPress should be functional and installable at
http://app.local. Make sure that WordPress can successfully connect to the MySQL
database so that the installation works correctly.
# Task 2: Custom Ingress-NGINX Lua Plugin
Using the custom ingress-nginx Lua plugin, configure ingress-nginx to redirect all 404
(Not Found) responses to google.com.
●​ This should apply to any incoming request where the ingress-nginx resource is not
found.
Expected Result: Visiting http://app.local/notfound, should redirect to google.com
# Task 3: Monitoring
●​ Deploy Prometheus, Loki, and Grafana along with Promtail (or Alloy) declaratively with
FluxCD.
●​ Configure logs from Kubernetes pods (e.g., WordPress, ingress-nginx, etc.) to be sent to
Loki via Promtai/Alloy.
●​ Set up a Grafana dashboard to visualize WordPress pod logs.
●​ Export the Grafana dashboard as a JSON file.
Expected Result: Grafana should be accessible at http://app-monitor.local
