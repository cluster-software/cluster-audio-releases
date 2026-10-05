# Cluster Audio

Native microphone and speaker companion for human Cluster Dialer calls. Runs on the computer with the microphone; the calling agent may run elsewhere.

Install with Python 3.11+ and uv:

```sh
uv tool install "https://github.com/cluster-software/cluster-audio-releases/releases/download/v0.1.0/cluster_audio-0.1.0-py3-none-any.whl#sha256=b57015f049bc232f9b41b3d31e68715ba8d4cfc4603e1262b1daa9ff5d9d0c4f"
cluster-audio devices
```

Register the installed executable as a local stdio MCP server with the `mcp` argument. Keep the hosted Cluster MCP connection for call controls. Linux needs PortAudio (commonly libportaudio2); macOS and Windows receive it through the audio dependency. Use headphones and allow OS microphone access when prompted.

The wheel includes only the audio client and standard Python package metadata. No private repository access or GitHub login is required. SHA256SUMS is supplied alongside the wheel.

## Agent setup

Ask the connected Cluster agent to use native audio. Cluster calling readiness provides the official wheel URL and setup instructions. The agent should reuse an existing microphone connection, or offer browser and native audio when none is ready.

If the calling agent runs in the cloud, run the companion on the computer with the microphone. A local agent can connect it under the same Cluster user and workspace; the cloud agent then discovers the ready session.

No phone call is placed by installing or starting this companion. The hosted Cluster MCP controls calling and credits.
