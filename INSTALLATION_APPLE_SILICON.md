```sh
# Proper way
uv sync

# Traditional way
uv venv --python 3.11
source .venv/bin/activate
uv pip install chatterbox-tts==0.1.7
uv pip install peft
```

# [Temporary PEFT workaround](https://github.com/resemble-ai/chatterbox/issues/198#issuecomment-3083054072)
- Open `.venv/lib/python3.11/site-packages/chatterbox/tts_turbo.py` and `.venv/lib/python3.11/site-packages/chatterbox/tts.py`
- Navigate to the line `self.watermarker = perth.PerthImplicitWatermarker()`
  - **Replace** with `self.watermarker = perth.DummyWatermarker()`