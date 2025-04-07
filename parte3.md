## Análisis del certificado SSL de pages.github.io

![github](/img/image3.png)

En base al informe SSL para `pages.github.io`, el certificado es considerado válido y obtiene una calificación general de **A**, lo cual refleja un alto nivel de seguridad en la configuración del sitio. A continuación se detallan los motivos que justifican esta verificación positiva:

---

###  Características del certificado

**1. Algoritmo y tamaño de clave**  
- **Algoritmo utilizado:** SHA256 con RSA  
- **Tamaño de clave:** 2048 bits  
Esto asegura un nivel de cifrado robusto y actualizado. No se detectaron claves débiles ni vulnerabilidades relacionadas.

**2. Período de validez**  
- **Inicio:** 18 de febrero de 2025  
- **Expiración:** 18 de febrero de 2026  
El certificado está dentro de su período de vigencia, lo cual es esencial para que sea considerado confiable.

**3. Entidad emisora**  
- **CA emisora:** Sectigo RSA Domain Validation Secure Server CA  
Una autoridad de certificación ampliamente reconocida y de confianza.

**4. Cobertura de dominio**  
- **Nombre común (CN):** `*.pages.github.io`  
- **Dominios alternativos:** `*.pages.github.io`, `pages.github.io`  
Esto garantiza que cubre correctamente tanto el dominio principal como los subdominios.

---

###  Seguridad adicional

**1. Soporte para TLS 1.3**  
El servidor utiliza TLS 1.3, la versión más moderna y segura del protocolo, lo que mejora el rendimiento y refuerza la protección ante ataques.

**2. Política CAA configurada**  
Existe una política de autorización de autoridades certificadoras (CAA) que especifica qué entidades están autorizadas para emitir certificados para el dominio. Esto añade una capa de seguridad adicional frente a certificados no autorizados.

**3. Evaluación técnica del informe**  
Todos los indicadores clave obtienen puntuaciones sobresalientes:
- Certificado: ✅
- Soporte de protocolo: ✅
- Intercambio de claves: ✅
- Fuerza del cifrado: ✅

---
## Análisis del certificado SSL de cacert.org

![cacert](/img/image4.png)

En base al informe SSL para `cacert.org`, el certificado es considerado **no válido** y obtiene una calificación general de **T**, lo cual indica problemas serios de confianza. A continuación se detallan los motivos que llevan a esta evaluación negativa:

---

###  Características del certificado

**1. Algoritmo y tamaño de clave**  
- **Algoritmo utilizado:** SHA512 con RSA  
- **Tamaño de clave:** 4096 bits  
Aunque el cifrado es fuerte y moderno, esto no compensa los problemas de confianza derivados de otros factores.

**2. Período de validez**  
- **Inicio:** 23 de marzo de 2024  
- **Expiración:** 23 de marzo de 2026  
El certificado está dentro de su período de vigencia, pero esto no basta para que sea confiable si no es reconocido por los navegadores.

**3. Entidad emisora**  
- **CA emisora:** CAcert Class 3 Root  
El principal problema es que esta CA **no está reconocida por la mayoría de los navegadores**, lo que causa que el certificado no sea confiable automáticamente para los usuarios.

**4. Cobertura de dominio**  
- **Nombre común (CN):** `www.cacert.org`  
- **Dominios alternativos:** incluye varios subdominios como `secure.cacert.org`, `wwwmail.cacert.org`, `www.cacert.net`, entre otros.  
La cobertura es técnicamente correcta, pero pierde validez por la falta de reconocimiento de la CA.

---

###  Problemas detectados

**1. Certificado no confiado por navegadores**  
El certificado **no es confiado por los navegadores principales**, lo cual significa que los usuarios recibirán advertencias de seguridad al intentar acceder al sitio.

**2. Uso de protocolos antiguos**  
El servidor soporta versiones obsoletas de TLS (1.0 y 1.1), lo cual degrada la seguridad general de la conexión.

**3. Falta de transparencia y validación extendida**  
- No se aplica Certificación Transparente (CT).
- No se ofrece validación extendida (EV).

**4. OCSP no utilizado**  
No se hace uso del protocolo OCSP (Online Certificate Status Protocol), lo cual impide verificar en tiempo real si el certificado ha sido revocado.

---
## Análisis del certificado SSL de revoked.grc.com

![revoked.grc.com](/img/image5.png)

En base al informe SSL para `revoked.grc.com`, el certificado es considerado **no válido** y obtiene una calificación general de **F**, lo cual indica problemas críticos de seguridad y confianza. A continuación se detallan los motivos que llevan a esta evaluación negativa:

---

### Características del certificado

**1. Algoritmo y tamaño de clave**  
- **Algoritmo utilizado:** SHA256 con RSA  
- **Tamaño de clave:** 2048 bits  
El tamaño de la clave es estándar y el algoritmo sigue siendo seguro, aunque no se considera de los más robustos comparado con opciones de mayor longitud como 4096 bits.

**2. Período de validez**  
- **Inicio:** 14 de agosto de 2024  
- **Expiración:** 14 de septiembre de 2025  
El certificado está dentro de su período de vigencia, sin embargo, esto no mejora su calificación debido a otros problemas graves.

**3. Entidad emisora**  
- **CA emisora:** DigiCert Global G2 TLS RSA SHA256 2020 CA1  
Aunque DigiCert es una CA reconocida, el estado de revocación del certificado lo vuelve no confiable.

**4. Cobertura de dominio**  
- **Nombre común (CN):** `revoked.grc.com`  
- **Dominios alternativos:** `revoked.grc.com`  
El certificado cubre correctamente el dominio principal, pero su revocación invalida esta cobertura.

---

### Problemas detectados

**1. Certificado revocado**  
El principal motivo de la calificación "F" es que el certificado ha sido **revocado**, lo que significa que ya no es válido y debe ser reemplazado de inmediato.

**2. OCSP y CRL indican revocación**  
Tanto el OCSP como las listas CRL reportan que el certificado ha sido revocado, lo cual es una señal clara de que no debe utilizarse.

**3. Uso de protocolos antiguos**  
El servidor **soporta versiones obsoletas** de TLS (1.0 y 1.1), lo cual degrada considerablemente la seguridad general.

**4. Soporte de cifrados débiles y configuración insegura**  
- El servidor utiliza parámetros de intercambio de claves **DHE (Diffie-Hellman)** con configuración no segura.  
- Se detecta **falta de soporte para configuraciones modernas** y recomendadas.

**5. Falta de transparencia y políticas modernas**  
- No se indica soporte para Certificación Transparente (CT).  
- Se detecta la ausencia de una política de autenticación de autoridades de certificación (CAA).

---

## Análisis del certificado SSL de xn--alestaavukatlk-lgc.com

![alestaavukatlik.com](/img/image6.png)

En base al informe SSL para `xn--alestaavukatlk-lgc.com`, el certificado es considerado **no válido** y obtiene una calificación general de **T**, la cual solo sería válida si se ignoran los problemas de confianza. A continuación se detallan los motivos que afectan negativamente su calificación:

---

### Características del certificado

**1. Algoritmo y tamaño de clave**  
- **Algoritmo utilizado:** SHA256 con RSA  
- **Tamaño de clave:** 4096 bits  
El tamaño de la clave es robusto y el algoritmo es seguro. Esto proporciona un buen nivel de cifrado.

**2. Período de validez**  
- **Inicio:** 12 de diciembre de 2024  
- **Expiración:** 10 de marzo de 2025  
El certificado **ya ha expirado** (hace 28 días), lo que lo vuelve completamente inválido a pesar de tener buenos parámetros criptográficos.

**3. Entidad emisora**  
- **CA emisora:** R10  
Esta autoridad certificadora **no es reconocida** por los principales navegadores, lo cual contribuye al estado de no confianza.

**4. Cobertura de dominio**  
- **Nombre común (CN):** `xn--alestaavukatlk-lgc.com`  
- **Dominios alternativos:** `www.xn--alestaavukatlk-lgc.com`, `xn--alestaavukatlk-lgc.com`  
La cobertura de dominios es técnicamente válida, pero pierde efecto por el estado expirado y la falta de reconocimiento de la CA.

---

### Problemas detectados

**1. Certificado expirado**  
El certificado ha expirado, lo que significa que no puede ofrecer una conexión segura. Esto invalida su uso inmediato.

**2. No es confiable para navegadores**  
El certificado **no es confiado por los navegadores modernos**, por lo que los usuarios recibirán advertencias de seguridad al acceder al sitio.

**3. Soporte limitado en navegadores**  
El sitio solo funciona correctamente con navegadores que soportan **SNI (Server Name Indication)**, lo cual puede excluir navegadores o dispositivos más antiguos.

**4. No se utiliza OCSP Must-Staple**  
Aunque se ofrece OCSP, no se implementa **OCSP Must-Staple**, lo que disminuye la capacidad de verificar en tiempo real la validez del certificado de forma obligatoria.

---

### Fortalezas detectadas

**1. Certificación Transparente (CT)**  
Sí se aplica Certificación Transparente, lo cual es una buena práctica para la seguridad y monitoreo público del certificado.

**2. Soporte de TLS moderno**  
El servidor **soporta TLS 1.3**, el protocolo más reciente y seguro para conexiones HTTPS.

**3. Política CAA configurada**  
Existe una política DNS CAA configurada correctamente para el dominio, lo que indica cierto cuidado en la configuración del entorno.

---

### Conclusión

Aunque el certificado de `xn--alestaavukatlk-lgc.com` cuenta con un cifrado fuerte y soporte para TLS 1.3, se encuentra **expirado** y **no es confiado por los navegadores modernos** debido a su emisor. Estos factores, sumados a la falta de medidas más estrictas como OCSP Must-Staple, resultan en una calificación negativa. Es imprescindible renovar el certificado con una CA confiable y mantener la configuración actualizada para garantizar una conexión segura.


