# solr-typo3-devbox

Vagrant recipe to provsion a box with TYPO3 6.2.x and 7.6.x to try TYPO3 and tx_solr

## How to start

1. Run 

```bash
vagrant up
```

2. add to you hosts file (/etc/hosts):

```bash
192.168.144.120   6.2.local.typo3.org
192.168.144.120   7.6.local.typo3.org
192.168.144.120   8.2.local.typo3.org
192.168.144.120	  dev-master.local.typo3.org
```

3. Login into TYPO3 6.2.x or 7.6.x / 8.2.x or dev-master:

* http://6.2.local.typo3.org/typo3/
* http://7.6.local.typo3.org/typo3/
* http://8.4.local.typo3.org/typo3/
* http://dev-master.local.typo3.org/typo3/


Username: admin
Password: supersecret

Afterwards in the backend requeue all pages and re index and then check the frontend.


4. Check solr:

* http://192.168.144.120:8081 For TYPO3 6.2
* http://192.168.144.120:8082 For TYPO3 7.6
* http://192.168.144.120:8083 For TYPO3 8.4
* http://192.168.144.120:8084 For TYPO3 dev-master


#Thx 
This box is based on and build with TYPO3.packer (https://github.com/Tuurlijk/TYPO3.Packer).
Thx to Michiel Roos for starting this.

This project was created by using my working time @dkd. If you want to support this join or
continue your sponsoring @ http://www.typo3-solr.com/en/sponsors/our-sponsors/


