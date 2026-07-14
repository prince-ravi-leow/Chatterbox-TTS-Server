```sh
uv venv --python 3.11
source .venv/bin/activate
uv pip install chatterbox-tts
uv pip install peft
```

# [Temporary PEFT workaround](https://github.com/resemble-ai/chatterbox/issues/198#issuecomment-3083054072)
- Open `/Chatterbox-TTS-Server/.venv/lib/python3.11/site-packages/chatterbox/tts_turbo.py`
- Navigate to the line `self.watermarker = perth.PerthImplicitWatermarker()`
  - **Replace** with `self.watermarker = perth.DummyWatermarker()`
