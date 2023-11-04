# samba-docker-compose
## I have set up a DIY NAS for myself. I use an old PC which uses lower TDP when running for long time used. 
## this NAS is used by a Windows machine and 2 iPads (use for watching high resolution videos)

## setup
- check uuid of disk by command: 
    >`sudo blkid`
- Following the docker-compose.yaml file, I have 2 storages, one is mounted to /home/hdd1tb_1 and the else is mounted to /home/hdd1tb_2.
![Alt text](fstab-ntfs.png)

- reload fstab 
    >`sudo mount -a`

- install docker engine, and run at folder which contains *docker-compose.yaml*
    > docker compose up -d
- when service is running like below -> it is done for use
    ![Alt text](container.png)


- setup firewall
    > sudo ufw allow 139

    >   sudo ufw allow 445

    >    sudo ufw allow 137

    >    sudo ufw allow 138

## Use on device
Notice that, my samba server has IP address is 192.168.1.135.
- for windows:
    ![Alt text](windows-setup.png)

    and the result
    ![Alt text](windows.png)

- for ipad: I use VLC to connect samba server
    ![Alt text](ipad.png)

Noticable things: in  yaml file, 

- `bear` is user
- `bearpasswd` is password     
![Alt text](yaml-file.png)