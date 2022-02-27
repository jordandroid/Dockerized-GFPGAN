# GFPGAN dockerized with its additional IDE

## Introduction
This github allow you to run GFPGAN really easily, just by running following steps in next sections.

This docker also provides an IDE which automatically starts to allow you to edit code regarding GFPGAN (to edit upscaling for example).

The IDE is **PyCharm 2021 community eddition**, and has access to the python environment of the python container for dev.

The dockerization connect these two containers by a dedicated local network, for now it does not bring functionnalities but could be if we used any kind of servers.

## How to use it 
You firstly need to check that **docker-compose** is installed and with a recent enough version to support Version 3 compose file.

- Clone this repo
- Put the image(s) that you want to restore in the folder inputs_tests folder
- Move inside cloned folder
- Run commande : docker-compose up --build

You can use them separately (just build both together and run as separate containers, or both at same time. The best advantages to run both at same time is that you can edit with PyCharm and directly restart GFPGAN docker service to see results of new version. (with new terminal window using docker restarts on project_python_gan container)

I tried to include a shared environment (one image picking environment from the second one) but unfortunately, it did not worked.

GFPGAN application automatically start with docker-compose up, you can also launch an iteractive terminal with docker run and then use following command to apply GFPGAN : python inference_gfpgan.py --save_root results --upscale 2 --test_path inputs_tests

It can takes some times but your images should be restored in restore folder and the dev tool (PyCharm) should be launched.

## License and Acknowledgement

GFPGAN dockerized is released under Apache License Version 2.0.

## BibTeX

    @InProceedings{wang2021gfpgan,
        author = {Xintao Wang and Yu Li and Honglun Zhang and Ying Shan},
        title = {Towards Real-World Blind Face Restoration with Generative Facial Prior},
        booktitle={The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
        year = {2021}
    }

## Contact

If you have any question, please email `jordan.jouanchicot@gmail/com`.
