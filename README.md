# 📦 Image Classification Pipeline with AWS Step Functions
This project demonstrates a complete serverless machine learning workflow using Amazon SageMaker, AWS Lambda, and Step Functions to:

1. Serialize and load image data from S3
2. Perform image classification via a model endpoint
3. Filter out low-confidence predictions

# 🧰 Components
## ✅ AWS Lambda Functions

| Function                       | Purpose                                                             |
| ------------------------------ | ------------------------------------------------------------------- |
| `serializeImageData`           | Loads image from S3, encodes as base64, returns as `image_data`     |
| `classifyImage`                | Sends the base64 image to a SageMaker endpoint, returns predictions |
| `filterLowConfidenceInference` | Filters predictions below a confidence threshold                    |

## ✅ AWS Step Function Workflow

```
A[Start] --> B[serializeImageData]
B --> C[classifyImage]
C --> D[filterLowConfidenceInference]
D --> E[End]
```

# 📝 Requirements
- boto3
- sagemaker
- jsonlines
- matplotlib, seaborn

# 💡 Author
Built by Rhea Mewadhari as part of AWS AI/ML Project 4.
For educational and prototyping use.
