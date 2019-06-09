flutter-devcontainer
--------------------

A Dockerfile & config for developing with [Flutter](https://flutter.dev/) and 
the [VS Remote - Containers](https://code.visualstudio.com/docs/remote/containers) 
extension. 

Usage: 
* Clone this repository `git clone https://github.com/MFAshby/flutter-devcontainer.git`
* Open it in VS Code `cd flutter-devcontainer; code .`
* Click 'Re-open in container' when prompted
* Wait for downloads to complete (this can take a while, it downloads java, android SDK
and flutter)
* Once the container has started, you can run `flutter create hello_world` to create a 
new project
* Running on a physical device is supported with `flutter run`, make sure you click the 
dialog on the device in order to trust the computer you are connecting from!

Please note that this container is set to run in 
[privileged mode](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities) 
in order to access USB devices on the host machine. You should be aware of the security 
implications of this. 

Please also note when you use this container you're automatically agreeing to the 
[Android SDK terms & conditions](https://developer.android.com/studio/terms)
