FROM phusion/baseimage:bionic-1.0.0
RUN apt update && apt install --no-install-recommends -y openjdk-8-jdk wget tar curl libglu1-mesa git unzip zip xz-utils openssh-client lib32stdc++6 usbutils
RUN wget https://dl.google.com/dl/android/studio/ide-zips/4.0.1.0/android-studio-ide-193.6626763-linux.tar.gz \
&& mkdir -p /android-studio \
&& mv android-studio-ide-193.6626763-linux.tar.gz /android-studio \
&& cd /android-studio && tar -xzf android-studio-ide-193.6626763-linux.tar.gz && rm android-studio-ide-193.6626763-linux.tar.gz
RUN curl -L https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_v1.20.4-stable.tar.xz | tar -C /opt -xJ
RUN mkdir project && cd /project && git clone -b facebook https://github.com/angelicrf/flutter.git 
ENV PATH $PATH:/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk:/android-studio/android-studio/bin:/android-studio/android-studio
RUN flutter upgrade
CMD /android-studio/android-studio/bin/studio.sh
