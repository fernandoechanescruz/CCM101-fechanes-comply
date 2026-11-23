# MinIO Deployment Documentation

## Docker Command Used
```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
elestio/minio server /data --console-address ":9001"
```

## Port Used to Access the Web Console
Port **9001**. I opened the MinIO Web Console in the browser by going through the "Traffic/Ports" tab in KillerCoda.

## Bucket Created
**client-photos**

## What the -e Flags Did
The `-e` flag passes environment variables into the container when it starts. In this command:
- `MINIO_ROOT_USER=cloudadmin` defines the admin username for logging in to the MinIO console
- `MINIO_ROOT_PASSWORD=CloudNova2026!` defines the matching admin password

Passing the credentials this way means they are not baked into the image. The same image can be reused for any deployment, and each one can have its own login details.
