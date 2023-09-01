FROM hungnb94/androidsdklinux:1.0

USER root

# Install Android SDK Platform 31
RUN sdkmanager "platforms;android-31"

RUN mkdir -p ~/.android/
RUN touch ~/.android/repositories.cfg
RUN chmod -R 777 ~/.android