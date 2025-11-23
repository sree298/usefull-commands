# Git SSH Key Pair Setup

## Generate SSH Key in Windows (Using Git Bash)

Open **Git Bash** terminal and run the below command:

```bash
ssh-keygen -t rsa -C "pasumarthisrinu123@gmail.com"
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/ssh.png" />

## Verify the SSH key-pair
Run the below command:
```bash
ls -lrth ~/.ssh/
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/key.png" />

## SSH RSA private key matches a public key
Run the below command:
```bash
ssh-keygen -l -f ~/.ssh/id_rsa
```
Run the below command:
```bash
ssh-keygen -l -f ~/.ssh/id_rsa.pub
```

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/keyscompare.png" />

## SSH RSA Public key copy
Run the below command:
```bash
cat ~/.ssh/id_rsa.pub
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/publickey.png" />

## Configure SSH public key on GITHUB Website: https://github.com/

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/setting.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/ssh-gpc.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/keyadding.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/keyadded.png" />


## Verify the GITHUB connectivity
Run the below command:
```bash
ssh -T git@github.com
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/connected.png" />

## Create New Repo on Github
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/newrepo.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/repocreating.png" />






