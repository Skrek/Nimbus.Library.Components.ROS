# Nimbus.Library.Components.ROS


# Deployment CI

### branches:
once deploying into the `master` branch, all the environments will be updated with the modified components 
## Library Deployment Flow
### Prepare
* The job `create directory for modified components` use the script `.filter_only_updated_items.py` and collect all the items that has been modified compare to the last commit branch into a new directory (this new directory is available in the job artifact).

### test
In the `test` stage there are 3 jobs which are responsible to test that all the components are valid. 

each job execute the <a href="https://git.cognimbus.com/nimbus/nimbus.library.loader/-/tree/develop/script_cli/PushComponentsDevices">library.loader script</a> in test mode according to the environment make sure the user credentials and json files are valid as a `ComponentInfo` instance.
### deploy
The stage `deploy` contains 3 jobs for deploying modified components - each job deploy to another environment.
<a href="https://git.cognimbus.com/nimbus/nimbus.library.loader/-/tree/develop/script_cli/PushComponentsDevices">library.loader script</a>
</br>
</br>
In addition, there are 3 manual jobs for deploying all the components in the repository - each job use different environment.  

## Dependencies
the source code for the device/component deployment is located in https://git.cognimbus.com/nimbus/nimbus.library.loader. any changes in the deployment source code should be in this repository. 


