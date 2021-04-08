# kubernetes-stateful-examples

El repositorio contiene dos ejemplos de aplicación stateful funcionando, una utilizando el objeto "Deployment" de la API de Kubernetes y otro el objeto "StatefulSet".

Para probar el funcionamiento:

- Iniciar minikube. (Solo con un puerto mapeable por un problema de Wordpress)
- cd a la carpeta con el ejemplo a testear
- Inicia los servicios
- Escala, pausa, etc. para comprobar que el estado se mantiene
- Borra los servicios
- Deten minikube

``` sh
minikube start --extra-config=apiserver.service-node-port-range=31713-31713
cd (example_to_test)
kubectl apply -k ./
minikube service wordpress --url
echo Entra en la url y añade algun post a wordpress, cambia el tema etc.
kubectl scale deployment|statefulset wordpress --replicas=0
kubectl scale deployment|statefulset wordpress --replicas=2
echo Entra en la url y comprueba que el estado se mantiene. Posts, tema...
kubectl delete -k ./
minikube stop
```
