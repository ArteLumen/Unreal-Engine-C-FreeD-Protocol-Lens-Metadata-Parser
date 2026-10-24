Unreal Engine C++ FreeD Protocol & Lens Metadata Parser
A high-performance C++ module designed for Unreal Engine, enabling real-time parsing of the FreeD protocol for broadcast cameras, tracking systems, and virtual production LED volumes.

🚀 Features
Real-Time Binary Parsing: Decodes low-level 24-bit big-endian FreeD packets received via network sockets.

Lens Metadata Extraction: Instantly extracts zoom, focus, and positional metrics from physical broadcast lenses.

Unreal Engine Integration: Dynamically updates the virtual camera's Field of View (FOV) and focal length to match physical lens behavior with zero perceptible latency.

📂 Code Overview
This framework consists of two primary logic blocks:

ParseFreeDBinaryData: Handles network byte array decoding according to the standard FreeD protocol specification.

UpdateCameraLensFromMetadata: Maps extracted physical parameters directly to Unreal Engine's UCameraComponent.

⚙️ Installation & Usage
Copy the parser logic into your custom Unreal Engine C++ project source files.

Bind your network socket receiver (UDP/TCP listener) to feed the incoming byte stream (TArray<uint8>) into the parser function:


C++
float Zoom, Focus;
if (UFreeDParserLibrary::ParseFreeDBinaryData(IncomingPacket, Zoom, Focus))
{
    UpdateCameraLensFromMetadata(MyVirtualCameraComponent, Zoom);
}

🛠️ Requirements
Unreal Engine: 5.0 or higher.

Hardware / Protocol: FreeD compatible camera tracking system or encoder (e.g., Mo-Sys, Stype, or custom socket stream).

📄 License
This project is open-source and available under the Apache License.
