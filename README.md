# Whisper Medical Diarization

This project uses OpenAI's Whisper for speech-to-text transcription combined with speaker diarization to create structured medical transcripts and SOAP notes. It is designed for processing doctor-patient conversations or other multi-speaker audio, such as telehealth recordings.

## Features

* **Audio/Video Download** from YouTube via `yt-dlp`
* **Speech-to-Text** transcription with Whisper (word timestamps included)
* **Speaker Diarization** using `Resemblyzer` + DBSCAN clustering
* **Speaker Labeling** for clear conversation breakdown
* **Medical SOAP Note Generation** using Google Gemini
* **Token Count Analysis** with `tiktoken`
* **Interactive Medical Intake Assistant** for patient symptom collection

## Workflow

1. **Download audio** from a given YouTube URL or local file
2. **Transcribe** the audio with Whisper
3. **Identify speakers** using voice embeddings & clustering
4. **Format conversation** with `Speaker X:` labels
5. **Generate structured SOAP note** via LLM
6. *(Optional)* **Run interactive symptom intake chatbot**

## Requirements

Install dependencies inside your environment:

```bash
pip install git+https://github.com/openai/whisper.git yt-dlp resemblyzer pydub scikit-learn tiktoken
```

You will also need:

* Python 3.9+
* Google Gemini API key (for SOAP note generation)
* FFmpeg installed

## Usage

Open the Jupyter Notebook:

```bash
jupyter notebook whisper.ipynb
```

1. Update the audio/video URL in the notebook.
2. Run the cells in sequence.
3. View transcripts, speaker labels, and generated SOAP notes.

## Project Structure

```
whisper.ipynb    # Main notebook with all steps
```

## Example Output

**Transcript with Speakers:**

```bash
Speaker 0: Good morning, what brings you in today?
Speaker 1: I’ve been having chest pain for the last two days.
```

**Generated SOAP Note:**

```bash
S: Patient reports intermittent chest pain starting 2 days ago.
O: No visible distress, normal heart rate.
A: Possible angina vs. musculoskeletal pain.
P: ECG, chest X-ray, follow-up in 3 days.
```

## License

This project is for educational and research purposes only.
