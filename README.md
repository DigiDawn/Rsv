# Rsvfx

**Rsvfx** is a Unity example project that demonstrates how to connect an Intel [RealSense](https://realsense.intel.com/) depth camera to Unity's [Visual Effect Graph](https://unity.com/visual-effect-graph).

## Features

- Real-time Intel RealSense depth-camera input
- Point-cloud processing inside Unity
- Dynamic position and color attribute maps
- Integration with Unity Visual Effect Graph
- Real-time particle effects driven by depth-camera data

## System Requirements

- **Unity 2019.2 or later**
- **Intel RealSense D400 series** depth camera
- [Git](https://git-scm.com/) installed on the system

Git is required because the project uses external Unity packages imported through Git.

## How It Works

The [`PointCloudBaker`] component receives a point-cloud stream from an Intel RealSense device and converts it into two dynamically updated attribute maps:

- **Position Map** — stores the 3D position of each point.
- **Color Map** — stores the corresponding color information.

These maps can then be used by Visual Effect Graph through the **Set Position from Map** and **Set Color from Map** blocks.

This allows live RealSense data to be used in much the same way as attribute maps imported from a point-cache file.

## Data Flow

```text
Intel RealSense Camera
        │
        ▼
  Point Cloud Stream
        │
        ▼
  PointCloudBaker
        │
        ├──► Position Map
        │
        └──► Color Map
                │
                ▼
       Unity VFX Graph
                │
                ▼
      Real-Time Visual Effects
```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/DigiDawn/Rsv.git
```

### 2. Open the Project

Open the cloned project using a compatible version of Unity.

### 3. Connect the RealSense Camera

Connect an Intel RealSense D400-series camera to your computer.

Make sure the camera is recognized correctly by the system before launching the example scene.

### 4. Open the Example Scene

Open the included Rsvfx example scene in Unity.

### 5. Run the Project

Enter **Play Mode**.

`PointCloudBaker` will process the RealSense point cloud and provide live position and color information to the Visual Effect Graph.

### Which RealSense model works best?

The **Intel RealSense D415** is recommended because of its relatively high sample density.
