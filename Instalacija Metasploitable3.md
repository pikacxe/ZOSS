# Instalacija Metasploitable 3

>   ## Potrebni alati
>   ### [Vagrant][vagrant]
>   ### [VirtualBox-7.0][vb]❗❗ Isključivo verziju 7.0.X ❗❗

### Nakon instalacije potrebno je pokrenuti sledece komande u terminalu / powershell
### Linux users:
```bash
mkdir metasploitable3-workspace
cd metasploitable3-workspace
curl -O https://raw.githubusercontent.com/rapid7/metasploitable3/master/Vagrantfile && vagrant up
```
### Windows users:
```powershell
mkdir metasploitable3-workspace
cd metasploitable3-workspace
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rapid7/metasploitable3/master/Vagrantfile" -OutFile "Vagrantfile"
vagrant up
```

### Nakon završetka gore navedenih komandi dobijate VM unutar virtualbox okruženja. Pre pokretanje podesite *Network Adapter* na *Bridged Adapter*
> ## VM --> Settings --> Network --> Attached to: --> Bridged Adapter (Odabrati iz padajuće liste umesto podrazumevanog NAT)

### Pokrenite VM, kredencijali za logovanje su 
> - ### username: vagrant
> - ### password: vagrant
### Komanda za pronalazak IP adrese VM-a
### Linux users:
``` bash 
ip a
```
### Windows users:
```powershell
ip config
```

# Pokretanje novog skeniranja alatom *Nessus*
> ### Tokom kreiranje novog *Basic Network Scan* potrebno je uneti:
> - ### Novi naziv
> - ### Dobijenu adresu VM-a
> - ### U tabu *Credentials* odabrati *SSH* i tip authentifikacije *password*. Kredencijali su i ovde vagrant:vagrant

### Nakon kreiranja pokrenuti novo skeniranje (Metasploitable 3 VM treba biti aktivan pre pokretanja). Skeniranje traje ~10 min

[vb]: https://forum.virtualbox.org/wiki/Download_Old_Builds_7_0
[vagrant]: https://developer.hashicorp.com/vagrant/install?product_intent=vagrant
