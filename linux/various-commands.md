unknown
`du -m -d 1 -a | sort -n `

fixes disk errors
`Sudo Umount /dev/sdb4; sudo ntfsfix /dev/sdxX `
 
glances for server monitoring cpu,mem 
free look at the -+ buffers line is the accurate one 
 
`netstat -tulpn`
 
find public ip 
`dig +short myip.opendns.com @resolver1.opendns.com`
 
remove broken package from apt
`sudo dpkg --remove --force-remove-reinstreq hpccoinv2`

unknown
`echo manual | sudo tee /etc/init/<service_name>.override`
 
`dpkg -L PACKAGENAME`

verify
the message there is no indication the key belongs to the owner is normal. 
check exit status with echo $? to be 0 

`gpg --keyserver pgpkeys.mit.edu --recv-key XXX
gpg --verify xx.tar.gz.sig xx.tar.gz`
 
