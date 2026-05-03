
when code is updated we need to run these:

docker build -t abhisha-course .

docker tag abhisha-course:latest 991524241826.dkr.ecr.ap-south-2.amazonaws.com/abhisha-course:latest

docker push 991524241826.dkr.ecr.ap-south-2.amazonaws.com/abhisha-course:latest

kubectl rollout restart deployment deployment-course-abhisha -n cloudstudents


to get ingress dns:
kubectl get ingress ingress-course-abhisha -n cloudstudents


the ingress dns:
k8s-cloudstu-ingressc-84950b259f-13517551.ap-south-2.elb.amazonaws.com

to add new course:
curl -X POST http://k8s-cloudstu-ingressc-84950b259f-13517551.ap-south-2.elb.amazonaws.com/ \
  -H "Content-Type: application/json" \
  -d '{"id":"C05","name":"Advanced Cloud"}'

to show all course:
curl http://k8s-cloudstu-ingressc-84950b259f-13517551.ap-south-2.elb.amazonaws.com/courses

to show specific course:
curl http://k8s-cloudstu-ingressc-84950b259f-13517551.ap-south-2.elb.amazonaws.com/courses/C05

