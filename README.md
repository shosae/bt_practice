# bt_practice

ROS2 BehaviorTree.CPP 실습 및 예제 프로젝트

## 시작하기

이 저장소는 ROS2 환경에서 BehaviorTree.CPP를 활용한 행동 트리 실습을 위한 예제 프로젝트입니다.

### 1. 의존성 패키지 클론

아래 명령어로 필요한 패키지들을 워크스페이스의 `src` 폴더에 클론하세요:

```bash
cd ~/bt_practice/src

git clone https://github.com/BehaviorTree/BehaviorTree.CPP.git

git clone https://github.com/BehaviorTree/BehaviorTree.ROS2.git

git clone https://github.com/PickNikRobotics/generate_parameter_library.git

git clone https://github.com/PickNikRobotics/RSL.git

git clone https://github.com/PickNikRobotics/cpp_polyfills.git
```

### 2. 내 패키지 생성

아래 명령어로 내 패키지를 생성합니다:

```bash
cd ~/bt_practice/src
ros2 pkg create --build-type ament_cmake bt_practice_pkg --dependencies rclcpp std_msgs behaviortree_cpp behaviortree_ros2
```

### 3. 예제 코드 작성

`bt_practice_pkg/src` 폴더에 원하는 C++ 예제 파일을 추가하며 개발을 시작하세요.

예시:
```
bt_practice_pkg/
├── src/
│   └── bt_u2_ex2.cpp
├── include/
├── CMakeLists.txt
└── package.xml
```

### 4. 빌드

```bash
cd ~/bt_practice
colcon build
source install/setup.bash
```

### 5. 실행

```bash
ros2 run bt_practice_pkg bt_u2_ex2
```

---

## 참고 자료
- [soohwan-justin님의 tistory](https://soohwan-justin.tistory.com/97)
- [The Construct Robotics Institute](https://www.youtube.com/watch?v=KO4S0Lsba6I&t=1639s)
