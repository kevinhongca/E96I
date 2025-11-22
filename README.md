# Electric Bike Motion Classification Project

This project uses embedded machine learning and a SensorTile to recognize and classify six electric-bike riding motions based on IMU sensor data. A neural network processes rotation and acceleration patterns to determine the rider’s action in real time.

## Classified Motions

- **Turning Right**
- **Turning Left**
- **Accelerating**
- **Braking**
- **Biking Uphill**
- **Biking Downhill**

---

## How the System Works

Each motion is defined by a sequence of two states performed by the user. These sequences form the basis of the training data.

### State Definitions

| Motion | State Sequence |
|--------|----------------|
| **Turning Right** | Rotate right 45°, then rotate right another 45° |
| **Turning Left** | Rotate left 45°, then rotate left another 45° |
| **Accelerating** | Rotate forward 45°, then rotate backward 45° |
| **Braking** | Rotate backward 45°, then rotate forward 45° |
| **Biking Uphill** | Rotate backward 45°, then remain still |
| **Biking Downhill** | Rotate forward 45°, then remain still |

---

## Expected Sensor Conditions

The neural network classifies each motion using characteristic rotation and acceleration patterns:

### Turning Right
- Negative rotation in the *z*-axis  
- Large acceleration in the positive *x*-direction  
- Small acceleration in the negative *y*-direction  

### Turning Left
- Positive rotation in the *z*-axis  
- Large acceleration in the negative *x*-direction  
- Small acceleration in the negative *y*-direction  

### Accelerating
- Positive rotation in the *x*-axis followed by negative rotation in the *x*-axis  

### Braking
- Negative rotation in the *x*-axis followed by positive rotation in the *x*-axis  

### Biking Uphill
- Initial acceleration primarily in the negative *z*-direction  
- Later readings show acceleration in both negative *z* and negative *y*  

### Biking Downhill
- Initial acceleration primarily in the negative *z*-direction  
- Later readings show acceleration in both negative *z* and positive *y*  

---
