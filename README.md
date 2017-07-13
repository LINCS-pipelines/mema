# mema
Docker container for MEMA package
This docker image is built based on the latest validated MEMA package.
Here is how to obtain and run it:

```
sudo docker pull ucbd2k/mema
sudo docker run -d -p <an available port>:8787 -v </a/local/path/to/mount/>:</opt/> ucbd2k/mema
```

Then go to localhost:"available port" as specified above.
User name and password are rstudio/rstudio
