# gps_ws
This is a collection of "ubox_F9R" and "ntrip_client".
이 레포지토리는 기존의 두 레포지토리인 "ublox_F9R"과 "ntrip_client"를 통합한 것입니다.
[ublox_F9R](https://github.com/aktmdtkd/ublox_F9R)
[ntrip_client](https://github.com/aktmdtkd/ntrip_client)

GPS에 필요한 라이브러리 설치
> sudo apt update
> sudo apt install libasio-dev
> sudo apt install ros-humble-diagnostic-updater
> sudo apt install ros-humble-nmea-msgs

이 워크스페이스를 빌드 하고 소싱
> colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
> source install/setup.bash

GPS를 연결하기 위한 시리얼 포트 확인
> ls /dev/ttyACM*

파일 실행
이때 yaml 파일은 위치를 잘 고쳐서 사용해야 합니다.
> ros2 run ublox_gps ublox_gps_node --ros-args --params-file /your_path/ublox_config.yaml
> ros2 launch ntrip_client ntrip_client.launch.py params_file:=/your_path/ntrip.yaml
