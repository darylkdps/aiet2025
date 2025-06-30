These are the system and user prompts as highlighted in the paper.

Claude models accept the user prompt as a list of dicts, as shown in the "content" key here:
```
[
    {
        "role": "user",
        "content": [
            {"type": "text", "text": "the methodological framework instructions that will be cached", "cache_control": {"type": "ephemeral"}},
            {"type": "text", "text": "the survey question (not cached)"},
            {"type": "text", "text": "the survey response (not cached)"},
        ],
    }
]
```

The user prompt is implemented using a three-part structure. The methodological framework instructions do not change regardless of the survey question or response. The model is instructed to look for the content of the survey question and response using XML tags `<survey_question>` and `<response>`.
