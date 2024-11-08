**Server-Side Request Forgery (SSRF)** es una vulnerabilidad de seguridad en aplicaciones web que permite a un atacante manipular un servidor para que envíe peticiones HTTP arbitrarias a recursos internos o externos. En lugar de dirigirse al objetivo de la aplicación web, el atacante hace que el servidor actúe como un proxy, permitiéndole acceder a recursos a los que normalmente no tendría acceso.

# ¿Cómo funciona la SSRF?

Los ataques SSRF generalmente ocurren cuando una aplicación web acepta una URL externa como entrada, la valida de forma insuficiente, y la utiliza para hacer solicitudes en nombre del usuario. Los atacantes pueden explotar esta vulnerabilidad para:

1. **Escanear la red interna**: Al realizar solicitudes a direcciones IP internas y puertos, los atacantes pueden descubrir servicios internos y vulnerabilidades.
2. **Acceder a servicios protegidos**: Muchos servicios sensibles, como bases de datos, APIs internas y servicios de la nube (por ejemplo, AWS Metadata Service), están protegidos detrás de un firewall. SSRF puede permitir el acceso a estos recursos.
3. **Ejecutar código remoto (RCE)**: Si se encuentra una vulnerabilidad adicional en el servicio al que se accede, puede llevar a la ejecución remota de código.

[Video explicativo y demostrativo ](https://www.youtube.com/watch?v=Zyt7lUO3mY8)

