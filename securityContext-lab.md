Create a pod named pineapple that uses the pihole/pihole image. Mount an emptyDir volume to the 
directory at data/app. Files created on the volume should use the file system group ID 3000.

Shell to the running container and create a file called logs.txt in the directory at data/app.
List the contents of the directory and verify the fs group.
