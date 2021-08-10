docker network create unleash
docker run -e POSTGRES_PASSWORD=Go4thsas \
  -e POSTGRES_USER=unleash_user -e POSTGRES_DB=unleash \
  --network unleash --name postgres postgres
docker run -p 4242:4242 \
  -e DATABASE_HOST=postgres -e DATABASE_NAME=unleash \
  -e DATABASE_USERNAME=unleash_user -e DATABASE_PASSWORD=Go4thsas \
  -e DATABASE_SSL=false \
  --network unleash unleashorg/unleash-server



eksctl utils write-kubeconfig --cluster=dev-eks --kubeconfig=test2
export KUBECONFIG=test2
