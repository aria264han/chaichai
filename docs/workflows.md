# Workflows

This document describes the main workflows in the sanitized showcase version.

## 1. Video Teardown

Input:

- Short-video URL
- Target industry

Output:

- Teardown report
- Storyboard table
- Content structure analysis
- Editing logic
- Reusable creative method
- 3 adapted scripts for the target industry

Flow:

```text
Video URL + Industry
→ collect public video metadata
→ extract frames and audio
→ transcribe speech
→ analyze visual frames
→ align visuals and transcript
→ query industry knowledge
→ write teardown report
→ generate adapted scripts
```

## 2. Account Monitoring

Input:

- Industry account list

Output:

- Account report
- Video performance summary
- Content diagnosis
- Next-step recommendations

Flow:

```text
Industry account
→ collect recent video list
→ summarize performance
→ identify strong and weak topics
→ compare with industry knowledge
→ output account report
```

## 3. Script To Video

Input:

- Storyboard table
- Script
- Visual style requirements

Output:

- Material plan
- Editing parameters
- Generated or edited video

Flow:

```text
Storyboard
→ parse scene, copy, subtitle, transition, effects
→ map natural language to editing parameters
→ generate or collect material
→ edit video
→ export final video
```

Production API details, material sources, and send-out automation are intentionally removed.

## 4. Knowledge Archiving

Input:

- Teardown reports
- Account reports
- Debug reports
- Useful session conclusions

Output:

- Entity pages
- Concept pages
- Synthesis pages
- Debug pages

Flow:

```text
New output
→ classify by knowledge type
→ extract reusable claims
→ attach source reference
→ write to Wiki
→ reuse in later tasks
```

## 5. Debugging

Input:

- Error report
- Tool failure
- Model/API behavior issue

Output:

- Repro note
- Diagnosis
- Stable workaround
- Debug knowledge page

Rules:

- Keep debugging memory separate from business memory.
- Do not mix private business data with tool diagnosis.
- Promote only reusable technical conclusions.
