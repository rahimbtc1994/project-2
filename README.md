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

## DevOps corporate Phases
1. Phase 1 : 
   - Network env (privacy, isolation & security)
   - k8s cluster (for deploy) & scan it
   - Create multiple VMs (Sonr, Nexus, Jenkins, Monitoring)
2. Phase 2 :
   - Git repo (private)
   - Push code
3. Phase 3 :
   - CI/CD pipeline
   - Best practices
   - Security measures
   - Configure mail notif
4. Phase 4 :
   - Setup Monitoring tools -> app (system level + app level)

## PHASE 1
1. Using the AWS default VPC
2. Create a EC2 Security group 
   1. Inbound rules :
      - HTTP :
      - HTTPS : 
      - SMTP : not for use
      - SMTPS : email notification
      - SSH : 
      - 6443 : kubernetes cluster
      - 3000-10000 : to deploy apps
      - 30000-32767 : deployemnts of apps (using VMs as kubernetes cluster)
3. Create EC2 (3 instance for the k8s cluster)
   - IAM
   - T2.micro
   - key
   - security group
   - storage
   - rename them (master, slave-1, slave-2)
4. Configure EC2 instance (install k8s)