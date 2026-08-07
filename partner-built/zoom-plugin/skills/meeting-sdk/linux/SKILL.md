---
name: meeting-sdk-linux
description: "Zoom Meeting SDK for Linux - C++ headless meeting bots with raw audio/video access, transcription, recording, and AI integration for server-side automation"
user-invocable: false
triggers:
  - "linux meeting bot"
  - "headless zoom bot"
  - "meeting sdk linux"
  - "zoom raw recording linux"
  - "meeting transcription bot"
  - "zoom docker bot"
  - "pulseaudio zoom"
  - "meeting sdk raw data"
---

# Zoom Meeting SDK - Linux Development

Expert guidance for building headless meeting bots with the Zoom Meeting SDK on Linux. This SDK enables server-side meeting participation, raw media capture, transcription, and AI-powered meeting automation.

## How to Build a Meeting Bot That Automatically Joins and Records

Use this skill when the requirement is:
- visible bot joins a real Zoom meeting
- the bot records raw media itself
- or the bot triggers a Zoom-managed cloud-recording workflow after join

Skill chain:
- primary: `meeting-sdk/linux`
- add `zoom-rest-api` for OBF/ZAK lookup, scheduling, or cloud-recording settings
- add `zoom-webhooks` when post-meeting cloud recording retrieval is required

Minimal raw-recording flow:

```cpp
JoinParam join_param;
join_param.userType = SDK_UT_WITHOUT_LOGIN;
auto& params = join_param.param.withoutloginuserJoin;
params.meetingNumber = meeting_number;
params.userName = "Recording Bot";
params.psw = meeting_password.c_str();
params.app_privilege_token = obf_token.c_str();

SDKError join_err = meeting_service->Join(join_param);
if (join_err != SDKERR_SUCCESS) {
    throw std::runtime_error("join_failed");
}

// In MEETING_STATUS_INMEETING callback:
auto* record_ctrl = meeting_service->GetMeetingRecordingController();
if (!record_ctrl) {
    throw std::runtime_error("recording_controller_unavailable");
}

if (record_ctrl->CanStartRawRecording() != SDKERR_SUCCESS) {
    throw std::runtime_error("raw_recording_not_permitted");
}

SDKError record_err = record_ctrl->StartRawRecording();
if (record_err != SDKERR_SUCCESS) {
