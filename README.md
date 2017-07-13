## mema: Docker container for running MEMA vignettes in RStudio

This docker image is built based on the latest validated MEMA package (release v1.0.1 on 5-16-2017) to run the vignettes provided by MEP-LINCS on 5-17-2017 at [`https://github.com/MEP-LINCS/MEMA/tree/master/vignettes`](https://github.com/MEP-LINCS/MEMA/tree/master/vignettes).

---
To obtain and run the container:

```
sudo docker pull ucbd2k/mema
sudo docker run -d -p <available port>:8787 -v </a/path/to/mount/>:/opt/ ucbd2k/mema
```

Then through a browser go to ```<host url>:<available port>``` as specified above.
User name and password are rstudio/rstudio
