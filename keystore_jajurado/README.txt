creando la tarea de certificados digitales:
======================================================
Creacion del keystore: jajurado_keystore.jks psw del keystore: jajurado
keytool -genkey -alias cgc.jajurado.bancolombia.com -keystore jajurado_keystore.jks -keyalg RSA -sigalg SHA256withRSA -keysize 2048

Importando la cadena de confianza y despues el certificado de WMQ:
keytool -import -trustcacerts -alias ISSUINGBANCOLOMBIACA2 -file ISSUINGBANCOLOMBIACA2.cer -keystore jajurado_keystore.jks
keytool -import -trustcacerts -alias ISSUINGBANCOLOMBIACA -file ISSUINGBANCOLOMBIACA.cer -keystore jajurado_keystore.jks
keytool -import -trustcacerts -alias ROOTBANCOLOMBIACA -file ROOTBANCOLOMBIACA.cer -keystore jajurado_keystore.jks
keytool -import -trustcacerts -alias CAWSQMGRCGC01 -file CAWSQMGRCGC01.apps.ambientesbc.lab.cer -keystore jajurado_keystore.jks

Verificar expiración certificado:
keytool -list -v -keystore jajurado_keystore.jks