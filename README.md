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

Here’s a structured section for your README file:

---

## Results
Below are some key results from the model’s evaluation, as well as examples of generated captions.
### Evaluation Metrics

- **BLEU-1:** 0.5545
- **BLEU-2:** 0.3097

### Example Captions

Below are some examples of generated captions by the model compared to ground truth captions:

- **Image 1:** ![image](https://github.com/user-attachments/assets/6ea4d19d-2532-45fb-9ec6-9364e0b04118)
  - **Generated Caption:** [start group of people are walking down the street end]
  - **Ground Truth:** [start group of marines walking down the road with american flags and other military flags end
start color guard representing the various arms of the armed services march in parade end
start military section of parade is marching with many different flags end
start marines dressing uniform walking in parade carrying their colors end
start soldiers march up the street during parade end]

- **Image 2:** ![image](https://github.com/user-attachments/assets/6dc2c669-fb1f-44b0-be1c-ed99753c56b4)
  - **Generated Caption:** [start man in black shirt and black pants is singing into microphone end
]
  - **Ground Truth:** [start man wearing black leather jackets holds two microphones to his mouth while standing in front of orange and white sign end
start man on stage talking through microphone in black leather jacket end
start man in black leather jacket singing in to microphone end
start man in leather jacket sings into two microphones end
start man in black leather jacket is singing end]


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
