FROM hungnb94/androidsdklinux:1.0

USER root

# Install Android SDK Platform 31
RUN sdkmanager "platforms;android-31"

RUN mkdir -p ~/.android/
RUN touch ~/.android/repositories.cfg
RUN chmod -R 777 ~/.android
RUN keytool -genkey -v -keystore ~/.android/debug.keystore \
 -alias androiddebugkey -storepass android -keypass android -keyalg RSA -keysize 2048 \
 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"