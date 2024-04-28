# Dockerfile - Ubuntu

## Description

### Arborescence

```bash
.
├── Dockerfile_UbuntuFocal_Pack_1
├── Dockerfile_UbuntuFocal_Pack_2
├── Dockerfile_Z_test
└── README.md

1 directory, 3 files
```

### Images docker d'Ubuntu

- Image 1
	- Titre : Ubuntu Focal Pack 1
	- Image de bas : Ubuntu Focal Pack 1 (ubuntu:focal-20240416)
	- OS Version : Ubuntu 20.04
	- Fichier : Dockerfile_UbuntuFocal_Pack_1
	- Détails paquets inclus :
		- vim nano tree
		- curl wget net-tools
	- [Lien Docker Hub](https://hub.docker.com/repository/docker/ldumay/ubuntu_focal_pack_1)
- Image 2
	- Titre : Ubuntu Focal Pack 2
	- Image de bas : Ubuntu Focal Pack 2 (ubuntu_focal_pack_1:1.0.0)
	- OS Version : Ubuntu 20.04
	- Fichier : Dockerfile_UbuntuFocal_Pack_2
	- Détails paquets inclus :
		- locales language-pack-en-base 
		- libfontconfig1 fontconfig fonts-dejavu-core fonts-dejavu-extra
		- openjdk11
		- nginx
	- [Lien Docker Hub](https://hub.docker.com/repository/docker/ldumay/ubuntu_focal_pack_2)
		

## Construction

```bash
docker build . -t ldumay/ubuntu_focal_pack_1:1.0.0 -f Dockerfile_UbuntuFocal_Pack_1
docker tag ldumay/ubuntu_focal_pack_1:1.0.0 ldumay/ubuntu_focal_pack_1:1.0.0
docker push ldumay/ubuntu_focal_pack_1:1.0.0
docker build . -t ldumay/ubuntu_focal_pack_2:1.0.0 -f Dockerfile_UbuntuFocal_Pack_2
docker tag ldumay/ubuntu_focal_pack_2:1.0.0 ldumay/ubuntu_focal_pack_2:1.0.0
docker push ldumay/ubuntu_focal_pack_2:1.0.0
docker build . -t ubuntu_focal_pack_test:1.0.0 -f Dockerfile_Z_test
docker run --name test -it ubuntu_focal_pack_test:1.0.0 /bin/sh
```