# Agent instructions — building repositories

These rules apply whenever you create, fork, or edit a GitHub repository for this user. They override convenience. They do not override the user's explicit request in the current chat.

## 0. Verify first (mandatory)

Before implementing anything, search GitHub for real, actively maintained repositories in this exact domain. Analyze multiple high-quality repositories and their official documentation. Use them as factual implementation references. Do not invent libraries, APIs, commands, folder structures, features, or configuration options. If something cannot be verified, flag it instead of guessing. Build my repository based on verified patterns from those real projects, while keeping the implementation original and respecting each project's license.

Practical checks:

1. Search GitHub (`search_repositories` / `search_code`) for 2–4 actively maintained repos in the same domain (recent commits, docs, license).
2. Read official docs for any library or CLI you will use. Confirm package names, flags, and folder layouts exist.
3. Prefer copying / adapting a **verified** template over writing a graph, config, or API from memory.
4. If you cannot verify it, **stop and say so**. Do not ship a guess.
5. Keep the new work original (do not dump someone else's project verbatim unless the user asked to fork). Honor MIT/Apache/GPL terms; keep `LICENSE` + `NOTICE` when you fork.

## 1. Hardware default

User machine: **NVIDIA GTX 1660 Ti, 6GB VRAM**.

- Do not recommend models, resolutions, batch sizes, or pipelines that need more than ~5GB VRAM with headroom.
- Default local image gen: SD 1.5, 512×512, batch 1, `--lowvram`.
- Flux, SDXL, video, and 1024+ latents are **blocked** unless the user explicitly accepts OOM risk.

ComfyUI workflows: use https://github.com/genexis777-dot/comfyui-workflow-skill  
Copy `templates/6gb/*`, never invent node types, run `scripts/validate_workflow.py` before delivery.

## 2. Repo quality

- Public unless the user asks private.
- Real `README.md` with what it is, how to run, and what was **not** GPU-tested.
- Do not add files that are not needed.
- Do not commit secrets.
- Attribute upstream. Do not strip licenses.

## 3. Honesty

- "Valid" JSON/code that passed a checker is not the same as "ran on the 1660 Ti".
- Never claim a GPU test you did not run.
- Never invent a GitHub repo, star count, or API that you did not fetch.
