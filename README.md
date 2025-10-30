# AWS LLM Deployment - Medical Report Summarizer

## Project Overview

This project demonstrates the deployment of a Large Language Model (LLM) on AWS Infrastructure as a Service (IaaS) to create an intelligent medical report summarization application. The application leverages Google's FLAN-T5 model to generate concise summaries of doctor reports, extracting key findings, diagnoses, treatment plans, and follow-up recommendations.

**⚠️ Medical Disclaimer:** This application is not a substitute for a licensed medical professional. Please consult your physician before taking any medical decisions.

## Summary

This hands-on project showcases the complete lifecycle of deploying a generative AI application on AWS EC2 infrastructure. It implements an automated medical report summarization system using state-of-the-art instruction-tuned language models, demonstrating practical skills in cloud computing, machine learning operations, and infrastructure management.

The solution processes medical reports and generates structured JSON summaries containing key medical information, making it easier for healthcare professionals to quickly review patient information.

## Technical Architecture

<img width="850" height="452" alt="Screenshot 2025-10-29 at 9 21 50 PM" src="https://github.com/user-attachments/assets/265841f6-bb98-40a9-b32c-3d0811e65f3f" />

### Infrastructure
- **Cloud Provider:** Amazon Web Services (AWS)
- **Compute:** EC2 Instance (M7i-flex.large recommended for cost, c4.4xlarge for performance)
- **Operating System:** Ubuntu 22.04 LTS
- **Storage:** 30GB root volume
- **Python Environment:** Virtual environment with dependency isolation

### AI/ML Stack
- **Model:** Google FLAN-T5 (Instruction-tuned transformer model)
- **Framework:** Hugging Face Transformers
- **Deep Learning:** PyTorch
- **Hardware Acceleration:** Accelerate library for optimized inference

## Skills Demonstrated

### Cloud & Infrastructure
- ✅ AWS EC2 instance provisioning and configuration
- ✅ Linux system administration (Ubuntu 22.04)
- ✅ Storage management and optimization
- ✅ Cost optimization strategies (instance sizing, GPU/VRAM considerations)

### DevOps & Automation
- ✅ Environment setup automation
- ✅ Dependency management with pip and virtualenv
- ✅ Remote server configuration
- ✅ Shell scripting for deployment workflows

### Machine Learning & AI
- ✅ Large Language Model (LLM) deployment on IaaS
- ✅ Generative AI application development
- ✅ Model inference optimization
- ✅ Zero-shot and few-shot learning implementation
- ✅ Understanding of model quantization and distillation techniques

### Software Engineering
- ✅ Python application development
- ✅ Virtual environment management
- ✅ Package dependency resolution
- ✅ File I/O and JSON data handling
- ✅ Application testing and validation

### Healthcare Domain
- ✅ Medical report processing
- ✅ Clinical information extraction
- ✅ Healthcare data formatting and structure

## Key Features

### 1. **Intelligent Summarization**
   - Extracts key medical findings from doctor reports
   - Identifies diagnoses and treatment plans
   - Captures follow-up recommendations
   - Generates structured JSON output

### 2. **Model Selection: Google FLAN-T5**
   - Instruction-tuned for improved performance
   - Open-source and accessible
   - Available in multiple sizes (small, base, large, XL, XXL)
   - Enhanced zero-shot and few-shot capabilities

### 3. **Performance Optimization**
   - Model caching for faster subsequent runs
   - Instance sizing recommendations (M7i-flex.large vs c4.4xlarge)
   - First run: ~2.5 minutes (model download)
   - Subsequent runs: ~1 minute (M7i) / 10-15 seconds (c4.4xlarge)

### 4. **Scalability Considerations**
   - Batching for improved throughput
   - Quantization for reduced memory footprint
   - Distillation techniques for smaller model deployment
   - VRAM and memory overhead management

## Installation & Deployment

### Prerequisites
- AWS Account with EC2 access
- SSH access to EC2 instances
- Basic understanding of Linux command line

### Step-by-Step Deployment

#### 1. Launch EC2 Instance
```bash
# Configuration:
# - AMI: Ubuntu 22.04 LTS
# - Instance Type: M7i-flex.large (recommended) or c4.4xlarge (faster)
# - Root Storage: 30GB
# - Security Group: Allow SSH (port 22)
```

#### 2. Connect to Instance
```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

#### 3. System Setup
```bash
# Update system packages
sudo apt update

# Install unzip utility
sudo apt install unzip

# Install pip for Python 3
wget https://bootstrap.pypa.io/get-pip.py
sudo python3 get-pip.py
```

#### 4. Application Setup
```bash
# Create project directory
mkdir summarizer
cd summarizer

# Download application files
wget https://d6opu47qoi4ee.cloudfront.net/genAI/ccaws/flan/summarizer.zip
unzip summarizer.zip

# Set up Python virtual environment
sudo pip3 install virtualenv
virtualenv venv
source venv/bin/activate
```

#### 5. Install Dependencies
```bash
# Install required Python packages
pip3 install transformers torch accelerate
```

#### 6. Run Application
```bash
# Execute the summarizer
python3 app_tester.py
```

### Viewing Results

```bash
# Navigate to summaries directory
cd summaries

# List generated summary files
ls

# View summary content (use tab completion)
cat summary_<timestamp>.json
```

## Performance Metrics

| Instance Type | First Run (with download) | Subsequent Runs |
|--------------|---------------------------|-----------------|
| M7i-flex.large | ~2.5 minutes | ~1 minute |
| c4.4xlarge | ~30 seconds | 10-15 seconds |

## Project Structure

```
llm/
├── pgpccmay18.docx                    # Project documentation
├── Screenshot 2025-10-29...png        # Architecture/output screenshots
└── README.md                           # This file
```

## Technologies Used

- **Cloud Platform:** AWS EC2
- **Programming Language:** Python 3
- **ML Framework:** Hugging Face Transformers
- **Deep Learning:** PyTorch
- **Model:** Google FLAN-T5
- **OS:** Ubuntu 22.04 LTS
- **Package Management:** pip, virtualenv
- **Data Format:** JSON

## Cost Optimization Strategies

1. **Instance Sizing:** Start with M7i-flex.large for cost-effectiveness
2. **Model Caching:** First download caches the model locally
3. **Batching:** Process multiple reports in batches for efficiency
4. **Quantization:** Consider model quantization for reduced memory usage
5. **Spot Instances:** Use EC2 spot instances for non-critical workloads

## Future Enhancements

- [ ] Implement batch processing for multiple reports
- [ ] Add model quantization for reduced costs
- [ ] Create web interface for easier access
- [ ] Implement API endpoints (REST/GraphQL)
- [ ] Add support for multiple medical report formats
- [ ] Integrate with healthcare systems (FHIR/HL7)
- [ ] Deploy with containerization (Docker/Kubernetes)
- [ ] Add monitoring and logging (CloudWatch)
- [ ] Implement CI/CD pipeline
- [ ] Add unit and integration tests

## Learning Outcomes

Through this project, you will gain hands-on experience with:

1. **Cloud Infrastructure Management:** Understanding AWS EC2 instance types, storage, and cost optimization
2. **LLM Deployment:** Practical knowledge of deploying and running large language models
3. **Generative AI Applications:** Building real-world AI applications for specific domains
4. **MLOps Practices:** Environment management, dependency handling, and model deployment workflows
5. **Healthcare Technology:** Understanding medical data processing and clinical information extraction

## Author

Patrick Jones

## Repository

GitHub: [pjones-git/AWS_LLM_Deployment](https://github.com/pjones-git/AWS_LLM_Deployment)

## License

This project is created for educational purposes.

---

**Note:** This project demonstrates Infrastructure as a Service (IaaS) deployment patterns. For production healthcare applications, ensure compliance with HIPAA, GDPR, and other relevant regulations.
