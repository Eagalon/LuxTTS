Simple installation:
```
git clone https://github.com/ysharma3501/LuxTTS.git
cd LuxTTS
pip install -r requirements.txt
```

Usage:
```python
from zipvoice.luxtts import LuxTTS
lux_tts = LuxTTS('YatharthS/LuxTTS', device='cuda') ## change device to cpu for cpu usage
```

Infer:
```python
text = "Hey, what's up loser? I think you should shut up? You have NO dignity either way, ugh!"
prompt_audio = '/kaggle/input/voices/ElevenLabs_2025-11-02T22_31_30_Jessica_pre_sp100_s35_sb80_v3.mp3'

encoded_prompt = lux_tts.encode_prompt(prompt_audio, rms=0.001)
final_wav = lux_tts.generate_speech(text, encoded_prompt, num_steps=4, t_shift=0.9)

display(Audio(final_wav, rate=48000))
```
