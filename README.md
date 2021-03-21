# kuber__practice
1. git clone https://github.com/dockersamples/example-voting-app
2. export PROJECT_ID=tokyo-portal-304417
3. echo $PROJECT_ID
4. docker build -t gcr.io/${PROJECT_ID}/hello-app:v1 .
5. docker run --rm -p 8080:8080 gcr.io/tokyo-portal-304417/hello-app:v1
6. gcloud auth configure-docker
7. docker push gcr.io/tokyo-portal-304417/hello-app:v1
8. gcloud config set project $PROJECT_ID
9. gcloud auth list
10. gcloud container clusters create hello-cluster
11. kubectl create deployment hello-app --image=gcr.io/tokyo-portal-304417/hello-app:v1
12. kubectl scale deployment hello-app --replicas=3
13. kubectl autoscale deployment hello-app --cpu-percent=80 --min=1 --max=5
14. kubectl expose deployment hello-app --name=hello-app-service --type=LoadBalancer --port 80 --target-port 8080
15. kubectl get service
16. docker build -t gcr.io/tokyo-portal-304417/hello-app:v2 .
17. docker push gcr.io/tokyo-portal-304417/hello-app:v2
19. kubectl set image deployment/hello-app hello-app=gcr.io/tokyo-portal-304417/hello-app:v2
20. app address http://35.241.222.66/
