# build images
docker build -t REPOSITORY/dcos_mgmt/mesos-dns:v0.6.0 .

# Example Usage
# host networking (faster than docker's bridge networking)
docker run -d --net=host -v "$(pwd)/config.json:/config.json" -v "$(pwd)/logs:/tmp" REPOSITORY/dcos_mgmt/mesos-dns:v0.6.0

# bridge networking 
docker run -d -p 53:53/udp -p 8123 -v "$(pwd)/config.json:/config.json" -v "$(pwd)/logs:/tmp"
