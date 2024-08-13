
# Receipt OCR Project

This project utilizes the PaddleOCR library to perform Optical Character Recognition (OCR) on images, specifically focusing on receipts. The primary goal is to detect and extract text from images, which can then be used for various purposes, such as data extraction and analysis.

## Features

- **Text Detection and Recognition**: Extracts text from images, including bounding boxes, recognized text, and confidence scores.
- **Image Visualization**: Displays the images with drawn bounding boxes around the detected text.
- **Result Storage**: Saves the processed images with OCR results in a specified directory.

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository_url>
   cd receipt-ocr-project
   ```

2. **Install Dependencies**
   Ensure you have Python installed. Then, install the required libraries using pip:
   ```bash
   pip install paddlepaddle paddleocr
   ```

3. **Download Dataset**
   Download your dataset or use your own images. Place the images in an appropriate directory.

## How to Run

1. **Initialize OCR Model**
   - Load the PaddleOCR model:
     ```python
     from paddleocr import PaddleOCR
     ocr = PaddleOCR(use_angle_cls=True, lang='tr')
     ```

2. **Load and Process Images**
   - Load an image and run OCR:
     ```python
     img_path = '<path_to_your_image>'
     result = ocr.ocr(img_path)
     ```

3. **Visualize and Save Results**
   - Use the provided functions to visualize and save the OCR results:
     ```python
     save_ocr(img_path, '<output_directory>', result, '<font_path>')
     ```

## Example

Here's a simple example of running OCR on an image:

```python
from paddleocr import PaddleOCR
import cv2

# Initialize OCR
ocr = PaddleOCR(use_angle_cls=True, lang='tr')

# Load an image
img_path = 'path/to/your/image.jpeg'
result = ocr.ocr(img_path)

# Visualize and Save Results
save_ocr(img_path, 'output/directory', result, 'path/to/font.ttf')
```

## Contributing

If you'd like to contribute to this project, feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License.
