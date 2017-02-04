# QR REST API Container

Simple API that will encode and decode QR 2D barcodes.
Based on https://github.com/dwimberger/spark-qr

## Docker

1. Build image `docker build -t dwimberger/qr-api .`
2. Run the image with debug using  
   `docker run -d -p 4567:4567 dwimberger/qr-api`

## Encode QR code

```
  curl localhost:4567/qr/`uuidgen` > test.png
```

## Decode QR code

```
  curl -F "image=@test.png" http://localhost:4567/qr
```

## QR Prefix

Use the environment variable QR_PREFIX to generate QR codes with an arbitrary prefix (for example an URL).
