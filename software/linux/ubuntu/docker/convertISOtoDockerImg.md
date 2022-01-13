
### Convert ISO images to Docker images


#### Requirements

- `unsquashfs`
- `tar`
- `docker`
- `find`

#### Instructions

- Go to /tmp dir and create two folders:
    - `cd /tmp && mkdir rootfs unsquashfs`
- Mount the iso to rootfs as a loop device
    - `sudo mount -o loop [ISO PATH] ./rootfs`
    - What is a loop device?
- Find the filesystem.squashfs file
    - `find . -type f | grep filesystem.squashfs`
- Use unsquashfs to extract filesystem files to the unsquashfs folder
    - `sudo unsquashfs -f -d ./unsquashfs/ ./rootfs/casper/filesystem.squashfs`
- compress and import the image using docker
    - `sudo tar -C unsquashfs -c . | docker import - [USERNAME]/[IMAGE_NAME]`
        - A SHA256 hash will be returned.
- Test the docker image by running `/bin/bash` upon startup
    - `docker run -h ubuntu -i -t [USERNAME]/[IMAGE_NAME] bash`
- Assuming you are logged in, push your image to docker hub
    - `docker push [USERNAME]/[IMAGE_NAME]`



