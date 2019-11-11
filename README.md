# ipfs-cluster-private
IPFS cluster setup: 3 nodes

```bash
$ go get github.com/Kubuxu/go-ipfs-swarm-key-gen/ipfs-swarm-key-gen # IPFS private secret shared key generation tool
$ ipfs-swarm-key-gen > swarm.key # Generate secret key
$ mkdir ipfsA ipfsB ipfsC # Create IPFS directories
$ tee ipfsA/swarm.key ipfsB/swarm.key ipfsC/swarm.key <  swarm.key # All nodes configs should have same secret keys
$ docker-compose up -d ipfsA ipfsB ipfsC # Start ipfs service
$ docker-compose up -d clusterA clusterB clusterC # start cluster service
```
