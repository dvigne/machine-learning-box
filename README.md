![Florida Polytechnic University](https://floridapoly.edu/wp-content/themes/floridapolytechnic/images/home_logo.png)
# Local Development Environments Utilizing Virtual Machines
## Machine Learning

### Required Software
In order to run the local development box, both Vagrant and Virtual Box are required. You may find the downloads available below.
1. Virtualbox
  * https://www.virtualbox.org/wiki/Downloads
2. Vagrant
  * https://vagrantup.com
3. Git SCM
  * https://git-scm.com/downloads

### Cloning the Repository
In order to get the configuration files required you must either clone this repository or download the zip file from above,

To clone the repository use:
```
git clone https://github.com/dvigne/machine-learning-box.git && cd machine-learning-box
```

### Configuring the box
Once you have cloned the box there will be a `Vagrantfile` for configuring the virtual machine and an `init` script responsible for creating the directory structure required for shared folders between your host computer and the virtual machine.

First download the box:
```
vagrant box add dvigne/machine-learning-box
```
Run the init scripts below (optional)

For Windows:
```
init.bat
```
For Linux/Mac:
```
./init.sh
```

### Turning on the Lights
After you have the Vagrant Box Downloaded and shared folders configured go ahead and turn the virtual machine on with:
```
vagrant up
```
and then connect with:
```
vagrant ssh
```

### Connecting to Jupyter Notebook
After you have connected to your Vagrant box with `vagrant ssh` run `jupyter-notebook` to launch the Jupyter Notebook server. It will output a URL with a token that you can use to login to the Jupyter Notebook.
```
vagrant@ubuntu-xenial:~$ jupyter-notebook
[I 05:07:06.942 NotebookApp] Writing notebook server cookie secret to /run/user/1000/jupyter/notebook_cookie_secret
[I 05:07:07.207 NotebookApp] JupyterLab beta preview extension loaded from /home/vagrant/anaconda3/lib/python3.6/site-packages/jupyterlab
[I 05:07:07.207 NotebookApp] JupyterLab application directory is /home/vagrant/anaconda3/share/jupyter/lab
[I 05:07:07.215 NotebookApp] Serving notebooks from local directory: /home/vagrant/Code
[I 05:07:07.215 NotebookApp] 0 active kernels
[I 05:07:07.215 NotebookApp] The Jupyter Notebook is running at:
[I 05:07:07.215 NotebookApp] http://192.168.33.10:8888/?token=a90027c0bf67a09decce2b856d02f4026506695c9c1daec7
[I 05:07:07.215 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[W 05:07:07.216 NotebookApp] No web browser found: could not locate runnable browser.
[C 05:07:07.216 NotebookApp]

    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://192.168.33.10:8888/?token=a90027c0bf67a09decce2b856d02f4026506695c9c1daec7&token=a90027c0bf67a09decce2b856d02f4026506695c9c1daec7
```
In this example you would navigate to `http://192.168.33.10:8888/?token=a90027c0bf67a09decce2b856d02f4026506695c9c1daec7&token=a90027c0bf67a09decce2b856d02f4026506695c9c1daec7` in your favorite browser to begin creating notebooks.

### Profit
After performing the above, you should have access to a shared folder located in your home folder at `/home/vagrant/Code`. You may drag your hw/code to the mapped shared `Code` folder on your host operating system located in the root of the vagrant directory we cloned back at the "Cloning the Repository" to sync files between your virtual machine and host operating system. This allows you to edit in your favorite text editor and your changes will be reflected within the virtual machine to compile and test.

Happy coding! :heart:
