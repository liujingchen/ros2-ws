FROM osrf/ros:foxy-desktop
ARG WORKSPACE
ARG USERNAME
RUN apt update && apt install -y wget gdb vim ros-foxy-turtlesim
RUN useradd -m -u 1000 ${USERNAME} && usermod -aG sudo ${USERNAME} && \
    echo "%sudo  ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    echo "source /opt/ros/foxy/setup.bash" >> /home/${USERNAME}/.bashrc && \
    echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/${USERNAME}/.bashrc
USER ${USERNAME}
