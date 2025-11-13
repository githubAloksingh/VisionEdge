# VisionEdge - Real-Time Edge Detection Android App

VisionEdge is a powerful Android application that demonstrates real-time computer vision using OpenCV. The app processes live camera feeds and applies Canny edge detection algorithms to visualize edges in real-time, making it perfect for learning computer vision concepts and exploring image processing on mobile devices.

## 🌟 Features

- **Live Camera Preview** - View your device's camera feed in real-time
- **Real-Time Edge Detection** - Apply Canny edge detection algorithm on-the-fly
- **Dual View Modes** - Toggle between raw camera feed and processed output
- **High Performance** - Optimized OpenCV processing with OpenGL ES rendering
- **Material Design UI** - Clean, modern interface with Material Components

## 🛠️ Technical Stack

- **Language**: Java
- **Computer Vision**: OpenCV Android SDK 4.x
- **Camera API**: Android Camera2 API
- **Rendering**: OpenGL ES 2.0
- **UI Framework**: Material Components for Android
- **Min SDK**: Android 8.0 (API 26)
- **Target SDK**: Android 12 (API 31)

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- Android Studio (Arctic Fox or newer)
- Android NDK (r21 or higher)
- Git
- Android device with camera (or emulator with camera support)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/VisionEdge.git
   cd VisionEdge
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing project"
   - Navigate to the cloned directory

3. **Install OpenCV SDK**
   - Download [OpenCV Android SDK](https://opencv.org/releases/)
   - Extract the downloaded SDK
   - Copy the SDK to: `app/src/main/jniLibs/OpenCV/`

4. **Configure CMake (if using native code)**
   - Verify `CMakeLists.txt` has correct OpenCV paths:
     ```cmake
     set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/src/main/jniLibs/OpenCV/sdk/native/jni)
     find_package(OpenCV REQUIRED)
     ```

5. **Build the project**
   - Click "Build > Make Project" or press `Ctrl+F9`
   - Or use Gradle:
     ```bash
     ./gradlew assembleDebug
     ```

6. **Run the app**
   - Connect your Android device or start an emulator
   - Click "Run > Run 'app'" or press `Shift+F10`

## 📖 How It Works

VisionEdge uses a multi-layer architecture to process camera frames in real-time:

1. **Camera Layer** - Camera2 API captures frames via TextureView
2. **Processing Layer** - OpenCV processes frames using Canny edge detection
3. **Rendering Layer** - OpenGL ES renders the processed output
4. **UI Layer** - Material Design components provide user interaction

### Edge Detection Algorithm

The app uses the Canny edge detection algorithm with the following parameters:
- Lower threshold: 80
- Upper threshold: 200
- Sobel kernel size: 3x3 (default)

## 🎯 Usage

1. Launch the app
2. Grant camera permissions when prompted
3. Choose viewing mode:
   - **Open Camera** - View raw camera feed
   - **Show Processed Output** - View edge-detected output
4. Point your camera at objects to see edges highlighted in real-time

## 🔧 Configuration

### Adjust Edge Detection Sensitivity

Modify the Canny thresholds in `ProActivity.java`:

```java
// Lower threshold = more edges detected (more sensitive)
// Higher threshold = fewer edges detected (less sensitive)
Imgproc.Canny(mRgba, edges, 80, 200);  // Current values
```

### Change Camera Resolution

Update camera configuration in the activity:

```java
// Add to onCreate() method
cameraBridgeViewBase.setMaxFrameSize(width, height);
```

## 📂 Project Structure

```
VisionEdge/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/visionedge/detector/
│   │   │   │   ├── MainActivity.java       # Main launcher activity
│   │   │   │   ├── RawActivity.java       # Raw camera view
│   │   │   │   └── ProActivity.java       # Edge detection view
│   │   │   ├── res/                       # UI resources
│   │   │   └── AndroidManifest.xml
│   │   ├── androidTest/                   # Instrumentation tests
│   │   └── test/                          # Unit tests
│   └── build.gradle
├── gradle/
├── build.gradle
├── settings.gradle
└── README.md
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📋 Future Enhancements

- [ ] Add more edge detection algorithms (Sobel, Laplacian)
- [ ] Implement adjustable threshold sliders
- [ ] Add image capture and save functionality
- [ ] Support for different color spaces (HSV, Lab)
- [ ] Real-time FPS counter display
- [ ] Filter selection menu
- [ ] Video recording with filters

## 🐛 Known Issues

- App requires runtime camera permissions on Android 6.0+
- Performance may vary on low-end devices
- Emulator camera support may be limited

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

Created and maintained by [Your Name]

## 🙏 Acknowledgments

- [OpenCV](https://opencv.org/) - Open Source Computer Vision Library
- [Android Camera2 API](https://developer.android.com/reference/android/hardware/camera2/package-summary) - Modern camera framework
- [Material Components](https://material.io/components) - Material Design UI components
- [OpenGL ES](https://www.khronos.org/opengles/) - 3D graphics rendering

## 📞 Support

For issues, questions, or suggestions:
- Open an issue on [GitHub Issues](https://github.com/yourusername/VisionEdge/issues)
- Email: your.email@example.com

---

**Made with ❤️ using OpenCV and Android**
# VisionEdge
# VisionEdge
