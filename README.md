# The Ultimate CICD Corporate DevOps Pipeline Project | Real-Time DevOps Project

## Architecture Flow
1. Client create a Jira task/ticket
2. Ticket Assigned to a developer 
3. Developer write the source code test it locally 
4. If every thing is fine he will push it to Github repo
5. **DevOps** Engineer create a pipeline using Jenkins (stages)
   1. Stage 1 : compling the source code
   2. Stage 2 : running unit tests
   3. Stage 3 : run Sonarqube (code quality check, linitng. formating, ...)
   4. Stage 4 : run vuln scan using trivy
   5. Stage 5 : build/package the app
   6. Stage 6 : publishing artifacts to Nexus repo (release mngt)
   7. Stage 7 : build docker image
   8. Stage 8 : run vuln scan the docker image
   9. Stage 9 : publish docker image to registry
   10. Stage 10 : deploy the app using k8s +6 scan the cluster using kubeaudit
   11. Stage 11 : receive the email notification 
6. Monitorning the app using Node exporter and Grafana

