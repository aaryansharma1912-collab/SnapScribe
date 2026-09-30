SnapScribe
On-device meeting intelligence for consultants & case teams — built for the Snapdragon AI Lab Build & Present Challenge (Qualcomm x HP, via Unstop)
SnapScribe transcribes and summarizes confidential client/case-team conversations entirely on-device, on a Snapdragon-powered HP PC. No audio or text ever leaves the machine.
Why this exists
Cloud AI notetakers (Otter, Fireflies, Copilot) can't be used on confidential client calls under most firms' data-handling policies. SnapScribe solves the same problem — meeting notes and action items — without the cloud dependency, by running everything on the Snapdragon NPU.
How it works
	1.	Transcription — Whisper-Base-En / Whisper-Tiny-En from Qualcomm AI Hub Models, exported and run on the Snapdragon NPU.
	2.	Summarization — a small on-device language model, prompted to produce structured minutes: Key Points / Decisions / Action Items.
	3.	Interface — a lightweight Python desktop app: start/stop recording, live transcript view, export summary as Markdown.
Project structure
snapscribe/
├── README.md
├── requirements.txt
├── app/
│   ├── main.py          # app entrypoint / UI
│   ├── transcribe.py    # Whisper on-device wrapper (qai_hub_models)
│   ├── summarize.py     # on-device LLM summarization wrapper
│   └── utils.py
├── models/
│   └── export_models.md # notes/commands for exporting the AI Hub model builds used
├── demo/
│   ├── sample_audio.wav
│   └── sample_output.md
├── docs/
│   └── architecture.png
└── LICENSE
Setup
pip install qai_hub_models
# see models/export_models.md for the exact export commands used for this build
pip install -r requirements.txt
python app/main.py
Status
🚧 Built for the Snapdragon AI Lab Build & Present Challenge. See Snapdragon Brief Project Description.docx (submission doc) for full problem/solution writeup.
