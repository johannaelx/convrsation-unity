# ConVRsation (Unity)
Frontend for the **ConVRsation**, a VR-based learning application that integrates AI speech models to enable natural spoken dialogue with NPCs inside immersive environments.
The project explores how real-time voice interaction can support language learning in everyday scenarios such as a bakery or a friend's visit.

The corresponding backend required for voice processing and AI interaction is available in the [ConVRsation Backend repository](https://github.com/johannaelx/convrsation-backend).

ConVRsation can be used in two modes:
- Desktop mode (for testing without a VR headset)
- VR mode (Meta Quest 3) (recommended, full experience)

## Desktop Version

The Unity application can be run on the same machine as the backend or on a separate device (in that case, both must be in the same network).

### Setup
1. Open the project in Unity
2. **Enable** the XR Device Simulator in all scenes:
    - Assets/Scenes/MainMenu.unity
    - Assets/Scenes/BakeryScene.unity
    - Assets/Scenes/Freundschaftstreff.unity
3. Save the changes

### Run
1. Open MainMenu.unity
2. Press Play in the Unity Editor

### Controls
- Interaction is done via keyboard (mapped to VR controller inputs)
- Key bindings can be viewed in-game

## VR Version (Meta Quest 3)
This is the intended way to experience the application.

### Network Setup
Ensure the backend and headset are in the same network (e.g. Wi-Fi)
1. Open Assets/SpeechDialog/SpeechHttpClient.cs
2. Replace localhost with the local IP address of the backend machine, e.g.
  ```
  http://localhost:8000/conversation → http://192.168.x.xxx:8000/conversation
  ``` 
### Unity Setup
Make sure the XR Device Simulator is **disabled** in all scenes:
  - MainMenu.unity
  - BakeryScene.unity
  - Freundschaftstreff.unity

In some cases, the endpoint must also be updated directly in the Unity scenes:
1. Open the scenes:
    - Assets/Scenes/BakeryScene.unity
    - Assets/Scenes/Freundschaftstreff.unity
2. Select the SpeechManager object in the Hierarchy
3. In the Inspector, locate the Speech Http Client (Script)
4. Update the Endpoint URL accordingly

### Build & Run
1. Connect the Meta Quest 3 via cable
2. Use Build and Run in Unity

## Notes
- ConVRsation is optimized for Meta Quest 3
- Microphone access is required for voice interaction
- Controls are explained in the Main Menu (Introduction section)
