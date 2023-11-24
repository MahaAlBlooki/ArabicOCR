# OCR Arabic Text Recognition

This project focuses on Optical Character Recognition (OCR) for Arabic text, utilizing the TCM CLIP model for text region localization, a combination of custom preprocessing methods and a trained Tesseract OCR engine with specific support for Arabic language.

## Description

The script includes several key stages:
- Applying TCM CLIP model to generate oriented bounding boxes
- Evaluating TCM CLIP results in terms of precision, recall, F1 score, and average IoU
- Preprocessing images for OCR (cropping bounding boxes, greyscaling, enhancing contrast, binarization, and noise removal)
- Training Tesseract OCR with specified parameters
- Running baseline and trained Tesseract OCR on preprocessed images
- Evaluating OCR results in terms of precision, recall, F1 score, average IoU, average accuracy, and total distance

## Getting Started

### Dependencies

- Python 3
- Libraries: matplotlib, opencv-python-headless, editdistance, pytesseract, numpy, shapely
- Tesseract OCR with Arabic language support
- Additional requirements for CLIP TCM (see below)

### Environment Setup

#### CLIP TCM
Clone the TCM repository and install the specified versions of libraries/dependencies:

```bash
git clone https://github.com/wenwenyu/TCM.git
cd TCM/ocrclip
```

#### Tesseract Arabic OCR
Install Tesseract OCR and the Arabic language support using Homebrew (macOS):

```bash
brew install tesseract
brew install tesseract-lang
pip install pytesseract
```

Set the Tesseract command:

```bash
import pytesseract
pytesseract.pytesseract.tesseract_cmd = '/opt/homebrew/bin/tesseract'  # Adjust as needed
```

Clone the necessary repositories for training data and scripts:

```bash
git clone https://github.com/tesseract-ocr/langdata.git
git clone https://github.com/astutejoe/tesseract_tutorial.git
```

### Installing
Install required Python packages:

```bash
pip install matplotlib opencv-python-headless editdistance pytesseract numpy shapely
```

### Usage
- **Preprocess Images**: Follow the preprocessing steps outlined in the script.
- **Run Tesseract OCR**: Apply Tesseract OCR on the preprocessed images.
- **Evaluate OCR Results**: Use the provided metrics to evaluate the OCR performance.

### Training the Model
Run the following command for training on font-specific generated images:

```bash
TESSDATA_PREFIX=../tesseract/tessdata make training MODEL_NAME=arab START_MODEL=ara3 TESSDATA=../tesseract/tessdata MAX_ITERATIONS=5000
```

## Contributing
Contributions to this project are welcome. Please ensure that your code adheres to the project's standards and submit a pull request for review.

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

## Acknowledgments
Wenwen Yu's TCM project for the CLIP OCR component.  
Tesseract OCR community for providing robust OCR tools and resources.




