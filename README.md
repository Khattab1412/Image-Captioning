![image](https://github.com/user-attachments/assets/e1e8a79a-a733-4b63-8232-6c3bf9127712)# Image Captioning on Flickr Dataset

## Project Overview
This project focuses on generating image captions using a combination of pre-trained DenseNet121 and LSTM models. The goal is to create descriptive captions for images from the Flickr dataset by leveraging advanced deep learning techniques.

## Dataset
The Flickr dataset was chosen for its extensive collection of images and associated captions, making it suitable for training and evaluating image captioning models. The dataset was preprocessed to extract features and clean the text captions using various NLP techniques.

## Model Architecture
The model architecture includes:

- **Image Feature Extraction**: DenseNet121 (pre-trained on ImageNet) is used to extract image features, which are saved in `features.pkl`.
- **LSTM Model**:
  - **Image Feature Layers**: Process image features with dropout and dense layers.
  - **Sequence Feature Layers**: Process text captions with embedding, dropout, and LSTM layers.
  - **Combination Layer**: Merge image and text features, followed by additional dense layers.
  - **Output Layer**: Predict captions with a dense layer using softmax activation.

The model is compiled using categorical cross-entropy loss and the Adam optimizer.

## Training
- **Epochs**: 20
- **Batch Size**: 32
- **Data Generators**: Custom data generators are used for training and validation.
- The model is saved after each epoch with filenames in the format `model_checkpoint_{i+1}.h5`.

## Evaluation
The model is evaluated using BLEU scores:
- **BLEU-1**: 0.5545
- **BLEU-2**: 0.3097
- ![image](https://github.com/user-attachments/assets/8231dac1-360d-4983-92a6-3a0a2c3c8271)


## Text Preprocessing
Captions are preprocessed to ensure consistency and improve model performance:
- **Convert to Lowercase**: All captions are converted to lowercase.
- **Remove Special Characters**: Digits and special characters are removed.
- **Remove Extra Spaces**: Additional spaces are removed.
- **Add Start and End Tags**: Start and end tags (`'start'` and `'end'`) are added to each caption.
- **Filter Short Words**: Single-character words are filtered out.

The captions are then mapped and tokenized for use in the LSTM model.

## Implementation
The code relies on the following libraries:
- TensorFlow/Keras
- NumPy
- Pandas
- Matplotlib
- Pillow
- WordCloud

## Usage
To use the model, run the provided IPython notebook, which includes instructions for training and evaluating the model.

## Future Work
- Train the model on additional datasets with similar characteristics to explore performance improvements.
