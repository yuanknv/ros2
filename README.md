# ROS 2 with CUDA Buffer Backend

This is a ROS 2 Rolling workspace with the [rcl_buffer](https://github.com/nvcyc/rcl_buffer/tree/rolling-native-buffer) native buffer feature and the [cuda_buffer_backend](https://github.com/yuanknv/cuda_buffer_backend) plugin for zero-copy GPU memory sharing.

## Getting started

Install [Pixi](https://pixi.sh) for an isolated and reproducible environment:

```
curl -fsSL https://pixi.sh/install.sh | sh
```

Clone this repository:

```
git clone https://github.com/yuanknv/ros2.git && cd ros2
```

Run the following command to setup the environment, clone the sources, build, and run the tests:

```
pixi run test "cuda_buffer cuda_buffer_backend"
```

You can run `pixi task list` for additional commands available, or simply do `pixi shell` if you prefer to use `colcon` directly.

## Packages

| Package | Description |
|---|---|
| `cuda_buffer` | Core CUDA buffer implementation: memory pool, IPC manager, and user-facing `to_buffer`/`from_buffer` APIs |
| `cuda_buffer_backend` | Plugin registration via `pluginlib`, endpoint discovery, and descriptor serialization |
| `cuda_buffer_backend_msgs` | ROS 2 message definition for `CudaBufferDescriptor` |

See the [cuda_buffer_backend README](https://github.com/yuanknv/cuda_buffer_backend) for usage examples and IPC behavior details.
