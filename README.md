# dash_shield
# SSL Security Service

This package provides a single static method to implement SSL certificate pinning for Flutter applications using Dio, http, or Retrofit.

### Usage

1. **Attach SSL Certificate**:
   
   Attach the SSL certificate directly by calling the static method `attachSSLCertificate()`:

   ```dart
   // Using with Dio
   Dio dio = Dio();
   await SSLSecurityService.attachSSLCertificate('assets/certificates/mycert.pem', dio);

   // Using with http package
   http.Client client = await SSLSecurityService.attachSSLCertificate('assets/certificates/mycert.pem', http.Client());

   // Using with Retrofit (via Dio)
   final dio = Dio();
   await SSLSecurityService.attachSSLCertificate('assets/certificates/mycert.pem', dio);
   final retrofit = Retrofit(dio);  // Retrofit uses Dio internally.
