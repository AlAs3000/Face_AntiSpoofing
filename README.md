Face Anti-Spoofing Dataset
This repository contains the Face Anti-Spoofing dataset aimed at distinguishing between real human faces and printed (spoofed) faces captured under various lighting conditions and angles.
Directory Structure
.
├── README.md                     <- This file
├── Training                      <- Training data
│   ├── Real_AA                  <- Real images of person AA
│   ├── Photo_AA                 <- Printed images of person AA
│   ├── Real_BB                  <- Real images of person BB
│   └── Photo_BB                 <- Printed images of person BB
└── Testing                       <- Testing/Validation data
    ├── Real_AA
    ├── Photo_AA
    ├── Real_BB
    └── Photo_BB

• Training: Contains four folders (Real_AA, Photo_AA, Real_BB, Photo_BB), each with approximately 300 images.
• Testing: Contains the same four folders, each with about 80 images for evaluation.
Dataset Description
1. Real_AA and Real_BB:
   - Real faces of two individuals, captured under different angles and lighting variations.

2. Photo_AA and Photo_BB:
   - High-quality printed faces of the same individuals, also captured under varying angles and lighting conditions to simulate spoof attacks.
Usage
1. Clone the Repository:
   git clone https://github.com/YourUsername/Face-AntiSpoofing-Dataset.git
2. Organize the Data:
- Place the Training and Testing folders in your preferred data directory.
- Update the paths in your code or configuration files to point to these folders.

3. Train Your Model:
- Use any deep learning framework (MATLAB, TensorFlow, PyTorch, etc.) to load the images.
Example in MATLAB:

trainingFolder = 'Training';
testingFolder  = 'Testing';

imdsTrain = imageDatastore(trainingFolder, ...
    'IncludeSubfolders', true, 'LabelSource', 'foldernames');
imdsTest = imageDatastore(testingFolder, ...
    'IncludeSubfolders', true, 'LabelSource', 'foldernames');

% Optional split for training/validation
[imdsTrain, imdsVal] = splitEachLabel(imdsTrain, 0.8, 'randomized');

% Then use imdsTrain/imdsVal with trainNetwork or your chosen framework.

4. Augmentation (Optional):
- Apply rotations, flips, brightness adjustments, etc., to increase variability and improve generalization.
Contributing
Contributions in the form of new data, additional spoof scenarios, or improvements to the dataset structure are welcome. Please open an Issue or submit a Pull Request to discuss potential changes.
License
Free 
Contact
For questions or suggestions, please create an Issue in this repository or reach out via email at alihh@uomustansiriyah.edu.iq
