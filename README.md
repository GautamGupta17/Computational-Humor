# Computational-Humor

### Dataset 🗂️
This project utilizes a multimodal dataset specifically designed for humor rating in stand-up comedy clips. The data is collected from various sources including YouTube and online streaming platforms (mention specific platforms if applicable). Here's a breakdown of the data collection and feature extraction process:

- Data Collection: We gather stand-up comedy clips featuring various comedians and comedic styles.
- Laughter Detection: Laughter is extracted from the clips using audio processing techniques. Laughter timestamps are then manually labelled to create short segments containing pure laughter audio.
- Feature Extraction:
1. **Audio Features**: Laughter characteristics like pitch, intensity, and amplitude are analyzed to calculate mean and standard deviation for each segment.

   
2. **Video Features**: OpenPose is used to extract keypoint information from the video, capturing human body language and facial expressions potentially associated with humor.

 
3. **Text Features**: We utilize pre-trained text embedding models like GloVe, BERT, and RoBERTa to capture semantic humor cues from the comedian's spoken content.
This combination of audio, video, and textual features allows our model to comprehensively analyze stand-up comedy clips for humor detection.


### Model Architecture ⚙️
The core of our system is a Long Short-Term Memory (LSTM) based neural network architecture. Here's a breakdown of how it works:

- Separate Bi-LSTM Layers: The extracted features are fed into separate Bi-directional LSTM layers.
- Text embeddings are processed by one Bi-LSTM layer.
- Audio and video features are each processed by separate Bi-LSTM layers.
- Dense Layers: Each Bi-LSTM layer is followed by a dense layer for further feature transformation. The outputs from the individual pathways (text, audio, video) are then concatenated and fed into a final classification layer. This layer outputs a humor rating on a 10-point scale, ranging from "Neutral" to "Hilarious".
- By combining LSTMs with these different feature types, our model can effectively learn temporal patterns and relationships between laughter, visual cues, and spoken language, ultimately leading to a more comprehensive humor rating.

### Results 👁️‍🗨️
Our experiments demonstrate the effectiveness of the proposed multimodal approach for humor rating in stand-up comedy. We achieved promising results using different pre-trained text embedding models, as indicated by the Kappa scores:


![image](https://github.com/bhanmrinal/Computational-Humor/assets/97622240/2e8619c1-052f-452c-8580-fe6f21a7276b)


These scores showcase the model's ability to leverage both textual and non-textual cues to accurately rate humor. Additionally, you can include a visualization (like your Fig IV) depicting the humor rating scale applied to a sample clip to further illustrate the results.

### Future Scope 🔮
- Dataset Expansion: Expanding the dataset with a wider variety of comedians, comedic styles (including silent comedy), and languages can enhance the model's generalizability.
- Feature Contribution Analysis: Investigating the relative importance of different features (laughter, facial expressions, spoken content) in humor perception can provide valuable insights.
- Humor Marketing Applications: The system's ability to analyze humor could be applied to understand audience preferences in marketing and advertising, leading to more effective humor-based campaigns.
