# Ransom-DDoSer
## 🕵️‍♂️ Extorsión en la red: Mitigando 120 Gbps de Ransom DDoS en el core de Cabase

No es la primera vez que escuchamos sobre amenazas y extorsiones digitales, pero cuando el ataque va directo a los ISPs que interconectan la red nacional, la gravedad escala a otro nivel. 

Hace unos días, nos topamos con una campaña agresiva de un vector que los atacantes autodenominaron "RansomDdoser". 

### 👀 El Contexto: 
Varios ISPs conectados a Cabase empezaron a recibir notas de rescate exigiendo pagos en Monero (XMR) para no saturar sus enlaces. Al no ceder al chantaje, los atacantes cumplieron su promesa: lanzaron un ataque Distributed Denial of Service (DDoS) masivo y volumétrico que escaló rápidamente hasta alcanzar picos de **120 Gbps**. 

Para un proveedor de internet, un flujo de ese calibre no solo tumba los servicios de la empresa, sino que degrada la conectividad de miles de usuarios finales en cascada.

### 👌 El Despliegue de Emergencia
Ante la alerta, decidimos poner a prueba nuestra propia tecnología en primera línea de fuego. Colocamos nuestro **Zeus Firewall** justo al inicio de la red, actuando como el escudo principal antes de que el tráfico sucio tocara la infraestructura interna. 

### 🎩 La Lógica de Filtrado (Donde ocurre la magia)
Mitigar 120 Gbps en un entorno ISP requiere una lógica quirúrgica y ultraeficiente para no generar falsos positivos. Con el equipo aplicamos una premisa fundamental de la arquitectura de red:

> "Al ser un proveedor de servicios de internet (ISP), el tráfico legítimo residencial o corporativo es predominantemente *saliente y solicitado*. Por ende, todo paquete entrante masivo que NO haya sido solicitado previamente por las conexiones de los usuarios internos se clasifica automáticamente como anómalo".

Configuramos a **Zeus** para monitorear y realizar un seguimiento estricto de las tablas de estado de los flujos de conexión. El firewall tomó la instrucción de forma inmediata: **descartar en el acto todo tráfico entrante no solicitado**. 

### 🤓 El Resultado del Bloqueo
La capacidad de procesamiento de Zeus en el borde de la red hizo su trabajo sin pestañear:

* **Capacidad filtrada:** Hasta 120 Gbps de tráfico basura mitigados en tiempo real.
* **Impacto en memoria/CPU:** Parámetros totalmente estables gracias al descarte temprano de paquetes en el plano de datos.
* **Resultado final:** Los ataques se convirtieron en simple ruido de fondo, las amenazas en Monero quedaron en la nada y los ISPs continuaron operando a máxima velocidad sin enterarse del flood.

---

Este tipo de escenarios nos demuestra que no se trata solo de tener "ancho de banda" para aguantar los golpes, sino de contar con la inteligencia y el software adecuado para filtrar el tráfico en el borde antes de que sature tus recursos.

¿Tu infraestructura está preparada para soportar ataques volumétricos sin perder rendimiento? 

Si querés proteger tu red o conocer más sobre cómo implementamos Zeus Firewall en entornos críticos, escribinos a **hola@waugi.com** o por mensaje privado. ¡Trabajemos juntos en tu próxima demostración sin compromiso!
