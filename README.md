# Integrate jenkins to git lab with web hook concept


- You can trigger a build in Jenkins when you push code to your repository or create a merge request in GitLab.


## Configure the Jenkins server


- Install and configure the Jenkins plugin. The plugin must be installed and configured to authorize the connection to GitLab.


- Frist login to your jenkins server and make sure it is running


- On the Jenkins server, select Manage Jenkins > Manage Plugins.
![image](https://user-images.githubusercontent.com/97168620/219579535-046fa843-9436-4b6f-bd14-c02601848fd5.png)


![image](https://user-images.githubusercontent.com/97168620/219579955-d951fcc7-9ca1-4f92-8708-d1003ffa06a4.png)


- Then next click on the avilable plugins and  search `gitlab plugin` and install it it will provide the options these are `install without restart` and another one is `Download now and restart after`


![image](https://user-images.githubusercontent.com/97168620/219584208-3b4cf118-b114-4434-a01e-27c24858b6b1.png)


- Then next create a job/project on your jenkins instance

- After installation of gitlab plugin restart the jenkins plugin


## Configure the Jenkins project


- Set up the Jenkins project you intend to run your build on.


- On your Jenkins instance, go to `New Item`.


![image](https://user-images.githubusercontent.com/97168620/219613611-6c8e0e67-9f55-4d8c-9632-bb3e6816b8d5.png)


- Enter the project’s name as `mvn_test`


- Select `Freestyle_project` and select OK.


![image](https://user-images.githubusercontent.com/97168620/219614321-64141e46-0957-46dc-b8bf-b6cfd043e1da.png)


- Next, configure the project/job in `General` settings and give the description about the job/project.


![image](https://user-images.githubusercontent.com/97168620/219616330-f6095d49-0235-4554-b22e-8337f1aec5c5.png)


- In the source code management section give the url of the source code. That is the gitlab url of the repository. and provide credentials if required.


![image](https://user-images.githubusercontent.com/97168620/219616741-d9deb3c9-39dc-47f6-85a4-e2584de5f47d.png)


- After providing the source code url then next define the `Build Triggers`. In the build triggers section click on the `Build when a change is pushed to GitLab. GitLab webhook URL` it will show some default values.


- After defining the build triggers click on to `apply` and next click on to the `save` button.


![image](https://user-images.githubusercontent.com/97168620/219618671-3183eb3f-3e6a-4ac8-8282-84182075ded7.png)


## Configure the GitLab project


- First of all you can login to your gitlab and select your required project/repository.


- After that click on to `Repository settings` in the repository setting there is a one option  is called as a `integration`


- In the integration page it will showcase the different integrated tools under that you can select the `jenkins` and click on the jenkins,


![image](https://user-images.githubusercontent.com/97168620/219625625-08d4d30d-52bb-4955-9a2b-e9f648c56949.png)


- After clicking on the `Jenkins` it will redirect to the jenkins integration page. here you can click on the `Active` radial button. It will give multiple options.


- Here you can choose the required  trigger events that are pushes to the repository or  Trigger event when a merge request is created, updated, or merged.


- Paste the your jenkins url on the `Jenkins server URL` box. next provide your project name that is provided in Jenkins freestyle project in the `Project name` section.


- Provide your Jenkins username and password in the `Username` section and `Enter new password` after providing the username and password next click on the `Test settings` and `save changes`


![image](https://user-images.githubusercontent.com/97168620/219627794-f6eb14f0-6fb9-49a7-89b7-32fcba77a2b7.png)
