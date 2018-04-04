# solr-typo3-devbox 
# It is outdated, we'll use [Docker environment](https://github.com/TYPO3-Solr/docker-dev-environment) instead in near feature!

Vagrant recipe to provision a box with TYPO3 7.6.x / 8.7.x  to try TYPO3 and tx_solr

## How to start

1. Run 

```bash
vagrant up
```

2. add to you hosts file (/etc/hosts):

```bash
192.168.144.120   7.6.local.typo3.org
192.168.144.120   8.7.local.typo3.org
192.168.144.120   9.1.local.typo3.org
192.168.144.120	  dev-master.local.typo3.org
```

3. Login into TYPO3 7.6 / 8.7 / 9.1 :

* http://7.6.local.typo3.org/typo3/
* http://8.7.local.typo3.org/typo3/
* http://9.1.local.typo3.org/typo3/


Username: admin
Password: supersecret

Afterwards in the backend requeue all pages and re index and then check the frontend.


4. Check solr:

* http://192.168.144.120:8081 For TYPO3 7.6 (Solr 6.6)
* http://192.168.144.120:8083 For TYPO3 8.7 (Solr 6.6)
* http://192.168.144.120:8084 For TYPO3 9.1 (Solr 6.6)


#Thx 
This box is based on and build with TYPO3.packer (https://github.com/Tuurlijk/TYPO3.Packer).
Thx to Michiel Roos for starting this.

This project was created by using my working time @dkd. If you want to support this join or
continue your sponsoring @ http://www.typo3-solr.com/en/sponsors/our-sponsors/


