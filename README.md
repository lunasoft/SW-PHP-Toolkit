
![NET](http://php.net//images/logos/new-php-logo.svg)

##### Libreria para la generación de archivos PEM desde shell en PHP, consulta de atributos de los archivos PEM **SW SmarterWeb**

Compatibilidad
-------------
* PHP 5.2.1 o superior

Dependencias
------------
* [OpenSSL](http://openssl.org/)
* OpenSSL Nativo PHP
 
----------------
Instalaci&oacute;n
---------
Descargar el archivo PHP desde repositorio [SW-PHP-Toolkit](https://github.com/lunasoft/SW-PHP-Toolkit)
Una vez descargado mandar a llamar desde la ruta el archivo con include o algún otro metodo de PHP para llamar el archivo
```
Implementaci&oacute;n
---------
include('certificados.php');

// Generaremos los archivos PEM necesarios para trabajar con nuestras librerias
// este proceso solo se necesitar&aacute; hacer solamente cuando tengamos un certificado nuevo,
// por lo que en promedio ser&aacute; cada 4 a&ntilde;s cuando generariamos estos archivos

// Iniciamos la clase
$certificados = new Certificados();
// Generamos el archivo *.key.pem proporcionando la ruta del archivo key y la contrase&ntilde;a del mismo
$certificados->generaKeyPem('../sellado/recursos/LAN7008173R5.key', '12345678a');
// Generamos el archivo *.cer.pem porporcionando la ruta del archivo
$certificados->generaCerPem('../sellado/recursos/LAN7008173R5.cer');
// para obtener las fechas de los certificados llamamos las funciones correspondientes
$fechaInicio = $certificados->getFechaInicio('../sellado/recursos/LAN7008173R5.cer.pem');
$fechaFin = $certificados->getFechaVigencia('../sellado/recursos/LAN7008173R5.cer.pem');
// Obtenemos el n&uacute;mero del certificado
$noCertificado = $certificados->getSerialNumber('../sellado/recursos/LAN7008173R5.cer.pem');
// Obtenemos el certificado en base64 para llenar el atributo Certificado
$certificadoBase64 = $certificados->certificadoBase64('../sellado/recursos/LAN7008173R5.cer');
// En caso de querer obtener toda la información contenida en el archivo PEM, mandamos a llamar la siguiente función
$datosCertificado = $certificados->getDatosCertificado('../sellado/recursos/LAN7008173R5.cer.pem');
// El resultado puede parsearse como objeto para obtener un valor especifico
var_dump($datosCertificado);


```

Para mayor referencia de un listado completo de los servicios favor de visitar el siguiente [link](http://developers.sw.com.mx/).

Si deseas contribuir a la libreria o tienes dudas envianos un correo a **soporte@sw.com.mx**.
