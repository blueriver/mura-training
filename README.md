# Mura Training Docker Image

The [Mura Training Docker Image](https://hub.docker.com/r/stevewithington/mura-training) is specifically used for Official Mura Training.

**Please Note:** If you're looking for the "*Official*" Mura Docker image, please visit https://hub.docker.com/r/blueriver/muracms/.


# Get Up & Running

[Docker Desktop](https://www.docker.com/products/docker-desktop) must installed and running on your computer (*Desktop Community* edition is perfectly fine) prior to following the steps below.

## After Docker Desktop Has Been Installed

Follow the steps outlined below:

1. Clone the [Mura Training repository](https://github.com/stevewithington/mura-training) to your desktop
2. Launch your shell program and `cd` into the cloned `../mura-training/` directory
3. Run `$ docker-compose up`
    * Docker will then begin to do its thing
        ```
        Creating network "mura-training_default" with the default driver
        Creating volume "mura-training_vol_muradb" with default driver
        Pulling svc_muradb (mysql:5.7)...
        5.7: Pulling from library/mysql
        f7e2b70d04ae: Pull complete
        etc ...
        ```
    * The first time this is run, it will take awhile to finish. Once you see a notification about the `WEB CONTEXT`, the server should be ready and you may proceed to the next step.    

        ``` 
        mura_1        | [INFO ] runwar.context: ===========================================
        mura_1        | WEB CONTEXT (8c069df52082beee3c95ca17836fb8e2)
        mura_1        | -------------------------------------------------------------------
        mura_1        | - config:/root/serverHome/WEB-INF/lucee-web (custom setting)
        mura_1        | - webroot:/app
        mura_1        | - hash:8c069df52082beee3c95ca17836fb8e2
        mura_1        | - label:8c069df52082beee3c95ca17836fb8e2
        mura_1        | ===================================================================
        ```

4. Once the image is finished loading and the server is ready, launch a browser window and navigate to http://localhost:8008/.
5. **Important!** If this is the first time you have launched the site, navigate to http://localhost:8008/?appreload&applydbupdates and the site should now be populated with sample content.


### Mura Login Information

This image uses [Mura](https://www.getmura.com), an open-source digital experiences platform. To learn more about Mura, visit https://www.getmura.com.
* Admin: http://localhost:8008/admin/
* Username: `admin`
* Password: `P@55w0rd!`


### Lucee Login Information

This image uses [Lucee](https://lucee.org), the leading open-source CFML application server/engine. To learn more about Lucee, visit https://lucee.org.
* Admin: http://localhost:8008/lucee/admin/server.cfm
* Password: `P@55w0rd!`


# Companion Training Files

Official Mura Training uses the following additional resources and files for each segment of training.

* [Mura Documentation](https://docs.getmura.com)
    * Documentation used for each training segment.
* [Content Manager Training](https://github.com/stevewithington/mura-training/tree/master/www/training/1-admin)
    * Companion files used for the Admin/Content Manager Training segment (1 day)
* [Theme Developer Training](https://github.com/stevewithington/mura-training/tree/master/www/training/2-theme)
    * Companion files used for the Theme Developer Training segment (1 day)
* [Core Developer Training](https://github.com/stevewithington/mura-training/tree/master/www/training/3-core)
    * Companion files used for the Core Developer Training segment (3 days)


# Building Your Own Image

If you're attending training, please do *not* make any changes to the [Dockerfile](https://github.com/stevewithington/mura-training/blob/master/Dockerfile) or [docker-compose.yml](https://github.com/stevewithington/mura-training/blob/master/docker-compose.yml) file until the conclusion of your training. At that point, feel free to make your desired changes, then simply run the following from your command line:

```
  $ docker-compose build --no-cache
```