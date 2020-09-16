# Cluster_Load_Balancer
3 VM administradas por Vagrant, cada máquina tiene LXD instalado, serverLoadBalancer tiene instalado Haproxy, severWeb1 y serverWeb2 tienen Apache2

Orden en que se deben ir ejecutando los archivos de aprovisionamiento.

1. StartUpServidor.sh se ejecuta mediante aprovisionamiento Shell.
2. Se configura el archivo hosts de Ansible en WSL.
3. Se hace el envío de las claves id_rsa desde WSL hasta las máquinas de vagrant.
4. Se realiza pruebas de comunicación.
5. LXDInstall.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
6. Se configura el cluster
7. LanzarContenedores.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
8. Se configura lxdfan0 subnet.
9. InstalarPaquetes.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
10. BackupsContenedores.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
11. InstalarPaquetesBackups.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
12. RedireccionPuertos.yml se ejecuta mediante aprovisionamiento Ansible en WSL.
13. ConfigurarHaproxyLxdBalancer.yml se ejecuta mediante aprovisionamiento Ansible en WSL.

Recomendaciones
1. Cada vez que se enciendan las máquinas ejecutar los archivos EncerderLxd(.....).yml que se ejecuta mediante aprovisionamiento Ansible en WSL
2. para detener los contenedores ejecutar el archivo ApagarContenedores.yml que se ejecuta mediante aprovisionamiento Ansible en WSL
3. para Encender los contenedores ejecutar el archivo EncenderContenedores.yml que se ejecuta mediante aprovisionamiento Ansible en WSL
