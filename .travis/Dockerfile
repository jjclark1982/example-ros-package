FROM ubuntu:14.04

# Register ROS repository
RUN apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116 && \
echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list && \
echo "deb-src http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" >> /etc/apt/sources.list.d/ros-latest.list

ENV ROS_DISTRO indigo

# Install ROS Base and rosinstall
RUN apt-get update && \
DEBIAN_FRONTEND=noninteractive apt-get install -y \
    ros-${ROS_DISTRO}-ros-base \
    python-pip \
    python-rosinstall \
    python-software-properties && \
rm -rf /var/lib/apt/lists/*
RUN rosdep init

# Create nonprivileged user to run rosdep
RUN useradd --create-home --shell=/bin/bash rosuser
USER rosuser
RUN rosdep update

# Run jsk.rosbuild
USER root
ADD https://raw.github.com/jsk-ros-pkg/jsk_common/master/jsk.rosbuild /tmp/jsk.rosbuild
RUN yes p | bash /tmp/jsk.rosbuild ${ROS_DISTRO} setup-ros
RUN yes p | bash /tmp/jsk.rosbuild ${ROS_DISTRO} install-jsk-ros-pkg
# temporally removed from compiling
RUN rm -rf $HOME/ros/hydro/src/humanoid_stacks
RUN yes p | bash /tmp/jsk.rosbuild ${ROS_DISTRO} compile-jsk-ros-pkg
# RUN yes p | bash /tmp/jsk.rosbuild ${ROS_DISTRO} test-jsk-ros-pkg
USER rosuser


# Setup ROS environment variables globally
# RUN echo 'source /opt/ros/${ROS_DISTRO}/setup.bash' >> /etc/bash.bashrc
ENV BASH_ENV /opt/ros/${ROS_DISTRO}/setup.bash
ENV TERM xterm-color

# Run roscore by default
EXPOSE 11311
ENTRYPOINT ["/bin/bash", "-c"]
CMD ["roscore"]
