
Al acceder al servidor mediante HTTPS desde el navegador, aparece un mensaje de advertencia indicando que el certificado no es confiable.

![Advertencia](/img/image.png)

A pesar de la advertencia, es posible continuar y ver los detalles del certificado instalado.

Al revisar la información del certificado, se puede comprobar que ha sido generado correctamente y está activo.

![Certificado1](/img/image1.png)

Para comparar, a continuación se presentará un ejemplo de un certificado firmado por una autoridad certificadora, el cual no genera advertencias y es reconocido por los navegadores como válido.

![Certificado2](/img/image2.png)


# Comparación de certificados SSL

A continuación, se presentan las diferencias entre dos certificados SSL visualizados en dos entornos distintos. Uno corresponde al dominio `*.pages.github.io` y el otro a un servidor local con dirección IP `10.0.2.151`.

---

##  Certificado 1: `*.pages.github.io`

- **Emitido a:**
  - **Nombre común (CN):** `*.pages.github.io`
  - **Organización (O):** No incluido en el certificado
  - **Unidad organizativa (OU):** No incluido en el certificado

- **Emitido por:**
  - **Nombre común (CN):** Sectigo RSA Domain Validation Secure Server CA
  - **Organización (O):** Sectigo Limited
  - **Unidad organizativa (OU):** No incluido en el certificado

- **Período de validez:**
  - **Emitido el:** Martes, 18 de febrero de 2025, 01:00:00
  - **Vencimiento el:** Jueves, 19 de febrero de 2026, 00:59:59

- **Huellas digitales SHA-256:**
  - **Certificado:** `8da674a510e19c78759b48739e794cba3f4017f4be135d68708a43247cccd51d`
  - **Clave pública:** `4f9c823196c6a8e01667d4b85171294f2391302fd38ceb5d516f60c4259e01f6`

---

##  Certificado 2: `server certificados` (IP: `https://10.0.2.151`)

- **Emitido a:**
  - **Nombre común (CN):** `server certificados`
  - **Organización (O):** Rafael Alberti
  - **Unidad organizativa (OU):** RA

- **Emitido por:**
  - **Nombre común (CN):** `server certificados`
  - **Organización (O):** Rafael Alberti
  - **Unidad organizativa (OU):** RA

- **Período de validez:**
  - **Emitido el:** Lunes, 7 de abril de 2025, 11:47:06 AM
  - **Vencimiento el:** Martes, 7 de abril de 2026, 11:47:06 AM

- **Huellas digitales SHA-256:**
  - **Certificado:** `7d2245b1684b076075c00976f1e02a677ef824c55e59010fce436444a0ce5631`
  - **Clave pública:** `476cf580f14bb98ae28e940b1fbc14e0597d5b9880ba438fb7ee8bfab45f6b3`

---

##  Comparación

| Característica              | `*.pages.github.io`                                  | `server certificados`                                |
|----------------------------|-------------------------------------------------------|------------------------------------------------------|
| **Dominio/IP**             | `*.pages.github.io`                                   | `https://10.0.2.151`                                 |
| **Entidad emisora**        | Sectigo Limited                                       | Autofirmado (Rafael Alberti)                         |
| **Tipo de validación**     | Validación de dominio (CA confiable)                  | Certificado autofirmado                              |
| **Organización declarada** | No                                                   | Rafael Alberti                                       |
| **Validez**                | 1 año (feb 2025 - feb 2026)                           | 1 año (abr 2025 - abr 2026)                          |
| **Uso típico**             | Producción (GitHub Pages)                             | Desarrollo/local                                     |
| **Confianza en navegadores** | Alta (CA reconocida)                              | Baja o nula (no confiable sin agregar excepción)     |

---

## Conclusión

- El certificado de `*.pages.github.io` es un certificado **válido y confiable emitido por una autoridad certificadora reconocida (Sectigo)**. Es ideal para producción.
- El certificado del servidor local `10.0.2.151` es **autofirmado**, útil solo para entornos de **desarrollo** o pruebas internas, ya que no es confiable por navegadores sin agregar una excepción manualmente.

