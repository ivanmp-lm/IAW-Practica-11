---
description: >-
  En esta práctica se utilizará la utilidad WPScan para revisar las
  vulnerabilidades de la página web.
---

# Práctica 11 - WPScan

WPScan nos permitirá detectar todas las vulnerabilidades de nuestro Wordpress, escaneará la página web en busca de agujeros de seguridad que puedan ser utilizados de forma maliciosa y también nos avisará del software y componentes desactualizados del servidor.

Para empezar a utilizarlo se obtendrá un contenedor de docker con la utilidad instalada utilizando el siguiente comando:

```text
$ docker pull wpscanteam/wpscan
$ docker run -it --rm wpscanteam/wpscan --url http://DIRECCION-IP  --enumerate p
```

Donde "DIRECCION-IP" será la IP pública del servidor donde esté alojada la página a escanear.

![](https://raw.githubusercontent.com/ivanmp-lm/IAW/master/.gitbook/assets/image%20(14).png)

No obstante, se necesita una clave API para poder escanear las vulnerabilidades del sistema, para ello habrá que registrarse en WPScan para que se nos proporcione la misma, que tiene 50 usos gratuitos al día.

Para escanear utilizando la clave API se usará el siguiente comando:

```text
$  docker run -it --rm wpscanteam/wpscan --url http://DIRECCION-IP --enumerate --api-token API
```

La cual podemos encontrar aquí:

![](https://raw.githubusercontent.com/ivanmp-lm/IAW/master/.gitbook/assets/image%20(22).png)

El resultado:

![](https://raw.githubusercontent.com/ivanmp-lm/IAW/master/.gitbook/assets/image%20(13).png)

Como se puede ver aparecen un par de vulnerabilidades a causa del plugin "themeisle-companion" que está desactualizado, gracias a esta herramienta se podrá reparar la vulnerabilidad fácilmente.

Como se puede ver aparecen un par de vulnerabilidades a causa del plugin "themeisle-companion" que está desactualizado, gracias a esta herramienta se podrá reparar la vulnerabilidad fácilmente.

**Se ha adjuntado al repositorio el resultado completo del escaneo mediante el uso del siguiente comando:**

```text
udo docker run -it --rm wpscanteam/wpscan --url http://3.82.213.244 --enumerate --api-token zUra4O3ysc2vtuW0fshEchEYX0QFieQwXEe3TQnhCdA > resultado.txt
```

