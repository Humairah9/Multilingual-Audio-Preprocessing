# Multilingual-Audio-Preprocessing
I processed 50 Hausa audio files for a speech engine project, converting them to .wav, applying noise reduction, and segmenting by pauses. I organized the data and metadata, showcasing my skills in audio preprocessing and multilingual data handling.

# Table of Content 
- [Introduction](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#introduction)
- [Objectives](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#objectives)
- [Overview](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#overview)
- [Data Source](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#data-source)
- [Tools Used](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#tools-used)
- [Data Cleaning ad Transformation](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#data-cleaning-and-transformation)
- [Methodology](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#methodology)
- [Visual Insights](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#visual-insights)
- [Visualizations](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#visualizations)
- [Conclusion](https://github.com/Humairah9/Multilingual-Audio-Preprocessing/blob/main/README.md#conclusion)


![download (4)](https://github.com/user-attachments/assets/d65b5dce-452c-45f3-8957-fd9074944e14)

# Introduction
With the rebranding of our startup from Otondo Limited to Otondo Team Ltd, and under the direction of the newly appointed Acting Chief Marketing Officer, Oyenibi David Ariyo, our company is reinforcing its commitment to national standards on data privacy and protection. This report presents the end-to-end workflow undertaken during Week 3 of the TDI Challenge: the download, processing, annotation, and analysis of a 250-file audio dataset in line with Nigerian data compliance requirements.

# Objectives
- Process and prepare a clean, high-quality audio dataset
- Segment the audio into short clips for manual transcription
- Create structured metadata for each segment
- Perform exploratory data analysis
- Enable transcription by qualified native speakers
- Align all actions with Nigeria's data protection framework

# Overview
The project’s goal is twofold:
- Technical: Prepare and segment audio data for machine learning and transcription purposes.
- Regulatory: Ensure compliance with Nigeria's NDPR (Nigeria Data Protection Regulation) through proper handling, documentation, and consent-based transcription efforts.

# Data Source
- Dataset: A batch of 250 unique audio recordings provided via a secured download link.
- Format: Original format in .mp3
- Content: The audios include various native narratives, conversations, and literature readings, primarily in Nigerian indigenous languages.
- Confidentiality: Files are anonymized and managed in a privacy-compliant environment.

# Tools Used
The project utilized Python as the primary programming language for implementing all data processing tasks. Pydub was employed for audio loading, format conversion, and segmentation, while noisereduce was used to clean background noise from audio files. Librosa supported audio sampling and analysis. For data organization and export, pandas and openpyxl were used to structure metadata and save it in Excel format. Visualization and analysis were handled using matplotlib and seaborn. Additionally, wave was used to measure the duration of audio segments, and the os module facilitated file and directory automation.

# Data Cleaning and Transformation
- Noise Reduction
  
Using noisereduce and librosa, all files underwent background noise removal to enhance clarity and quality.
- Format Conversion
  
All .mp3 files were batch-converted to .wav format using pydub, as .wav provides higher fidelity for downstream processing.
- Audio Segmentation
  
  - Implemented via pydub.silence.split_on_silence()
  - Parameters:
     - min_silence_len = 700ms
     - silence_thresh = -40dB
  - Each audio was split into logical, content-based segments, excluding intros, outros, or unrelated portions.

# Methodology
Step 1: Audio Preprocessing
- Files downloaded and extracted into a designated working directory.
- Cleaned using a noise reduction pipeline.
- Converted to .wav format for compatibility and lossless quality.

Step 2: Segmentation
- Silence-based segmentation logic was applied to all audio files.
- Resulting files stored with unique IDs (audio_id) and catalogued.

Step 3: Metadata Generation
- Extracted features:
    - audio_id, audio_file_location, audio_length
    - speaker_name, speaker_gender, audio_category
    - audio_transcript (set as "Pending")
- Data saved to an Excel spreadsheet for downstream transcription.

# Visual Insights
- The dataset currently lacks topical differentiation, which could limit certain types of NLP or classification tasks. Future labeling could enrich the dataset.
- This skew should be considered in model training to avoid gender bias. Including more male or balanced content may be needed for fairness.
- The source data from these speakers was likely longer or more continuous. This can be helpful for training speaker-specific models or voiceprints.
- This confirms the gender skew and the need to diversify speaker demographics for general-purpose models.
- Mixed dialogues or instructional content may naturally span longer durations, which can influence segmentation and transcription complexity.
- Segmentation worked effectively to create short, manageable audio clips suitable for speech recognition or diarization tasks.

# Visualizations

![visual 1](https://github.com/user-attachments/assets/14de4598-1b1c-40d2-b7ad-f2119b6b9de5)

![visual 2](https://github.com/user-attachments/assets/aecf33cc-c4b4-4118-8ca9-f4cd1e29ae01)

![visual 3](https://github.com/user-attachments/assets/408ebccd-471a-46f5-8da6-746307aab0b3)

![visual 4](https://github.com/user-attachments/assets/202fcd30-391c-433a-8e82-a7fccca3620b)

![visual 5](https://github.com/user-attachments/assets/25728995-642d-4061-939b-26647f3b1d15)

![visual 6](https://github.com/user-attachments/assets/171e4039-62f1-4a13-91e4-680036d10535)

#  Conclusion
This report outlines a robust audio preprocessing pipeline and highlights key patterns in speaker demographics and audio structure. The workflow prepares the dataset for further tasks like transcription, classification, or speaker identification.

# Recommendations
- Add topic-level labels for audio segments to enrich analysis.
- Collect or augment with male speaker audio for better gender balance.
- Validate speaker annotations using embedding-based similarity (e.g., with pyannote.audio or Resemblyzer).
- Consider chunk length regularization for uniformity in model input.
