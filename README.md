# mema
Docker container for MEMA package.
This docker image is built based on the latest validated MEMA package (v1.0.1) to run the vignettes provided at 17-May-2017 here: `https://github.com/MEP-LINCS/MEMA/tree/master/vignettes`.
Here is how to obtain and run the container:

```
sudo docker pull ucbd2k/mema
sudo docker run -d -p <available port>:8787 -v </a/path/to/mount/>:</opt/> ucbd2k/mema
```

Then go to <host url>:<available port> as specified above.
User name and password are rstudio/rstudio
