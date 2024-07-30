---
  title: 'SwiftTestFile.swift'
  description: 'component description'
  pubDate: 'July 30, 2024'
  author: 'Carlos Polanco'
  ---
  
  
  
  # SwiftTestFile.swift
  # Code Explanation

### Functions:
1. **calculateBMI**:
   - **Parameters**: 
     - `weight`: Represents the weight of an individual in kilograms (Double data type).
     - `height`: Represents the height of an individual in meters (Double data type).
   - **Operation**: Calculates the Body Mass Index (BMI) using the formula `weight / (height * height)`.
   - **Return**: Returns the calculated BMI as a Double value.

2. **getHealthRecommendation**:
   - **Parameters**:
     - `bmi`: Represents the Body Mass Index (Double data type).
   - **Operation**: Provides a health recommendation based on the BMI value using a switch statement.
   - **Return**: Returns a String message based on the BMI range:
     - If BMI is less than 18.5: "Underweight - You should eat more nutritious food."
     - If BMI is between 18.5 and 24.9: "Normal weight - Keep up the good work!"
     - If BMI is between 25 and 29.9: "Overweight - Consider a balanced diet and exercise."
     - For any other BMI value: "Obesity - Consult a healthcare provider."

### Usage:
1. **Initialization**:
   - `weight = 70.0` (weight in kilograms)
   - `height = 1.75` (height in meters)

2. **BMI Calculation**:
   - Calculate the BMI by calling `calculateBMI(weight: weight, height: height)` function.

3. **Health Recommendation**:
   - Get the health recommendation based on the calculated BMI by calling `getHealthRecommendation(bmi: bmi)` function.

4. **Output**:
   - Print the calculated BMI and the health recommendation.

### Example Usage:
```swift
let weight = 70.0  // weight in kilograms
let height = 1.75  // height in meters

let bmi = calculateBMI(weight: weight, height: height)
let recommendation = getHealthRecommendation(bmi: bmi)

print("BMI: \(bmi)")
print("Recommendation: \(recommendation)")
```

### External Libraries/Dependencies:
- The code does not rely on any external libraries or dependencies. It is written in Swift and uses the Foundation framework for basic functionalities.
  
  ## Component Code
  ```jsx
  import Foundation

func calculateBMI(weight: Double, height: Double) -> Double {
    return weight / (height * height)
}

func getHealthRecommendation(bmi: Double) -> String {
    switch bmi {
    case ..<18.5:
        return "Underweight - You should eat more nutritious food."
    case 18.5..<24.9:
        return "Normal weight - Keep up the good work!"
    case 25..<29.9:
        return "Overweight - Consider a balanced diet and exercise."
    default:
        return "Obesity - Consult a healthcare provider."
    }
}

let weight = 70.0  // weight in kilograms
let height = 1.75  // height in meters

let bmi = calculateBMI(weight: weight, height: height)
let recommendation = getHealthRecommendation(bmi: bmi)

print("BMI: \(bmi)")
print("Recommendation: \(recommendation)")
  ```
  