# Electric Bike Motion Classification Project

Our Electric Bike Project uses neural networks to recognize and classify six distinct riding motions using a SensorTile and an Embedded ML system. The six motions are:

- **Turning Right**
- **Turning Left**
- **Accelerating**
- **Braking**
- **Biking Uphill**
- **Biking Downhill**

---

## How the System Works

The system classifies each motion using a short sequence of user-generated states, defined as follows:

| Motion | Expected State Sequence |
|--------|--------------------------|
| **Turning Right** | Rotate right 45°, then rotate right another 45° |
| **Turning Left** | Rotate left 45°, then rotate left another 45° |
| **Accelerating** | Rotate forward 45°, then rotate backward 45° |
| **Braking** | Rotate backward 45°, then rotate forward 45° |
| **Biking Uphill** | Rotate backward 45°, then remain still |
| **Biking Downhill** | Rotate forward 45°, then remain still |

---

## Expected Sensor Conditions

We expect the neural network to classify each motion based on the following sensor patterns:

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
- Later readings show acceleration in both the negative *z*- and negative *y*-directions  

### Biking Downhill
- Initial acceleration primarily in the negative *z*-direction  
- Later readings show acceleration in both the negative *z*- and positive *y*-directions  

---
