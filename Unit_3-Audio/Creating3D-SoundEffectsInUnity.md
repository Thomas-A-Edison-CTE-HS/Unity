**Activity Guide: Creating 3D Sound Effects in Unity**

---

**Objective**: In this activity, you will learn how to add, adjust, and experiment with 3D sound effects in Unity. By the end of this tutorial, you’ll understand the role of audio in world-building, developing atmosphere, and how to apply custom rolloffs to simulate realistic sound behavior in 3D spaces.

---

### **1. Overview**

The goal of this tutorial is to add sound to the waterfall in your Unity scene and fine-tune the audio to make it feel immersive. We will cover everything from adding the initial sound to experimenting with spatial effects and Doppler shifts.

---

### **2. Add the Waterfall Sound**

**Steps:**
1. In the Hierarchy, right-click and select **Audio > Audio Source**. Rename the audio source as “Waterfall Audio.”
2. Move the Audio Source to the bottom of the waterfall where it meets the pond.
3. Find the **AmbientWaterfall** audio clip in your Assets folder and assign it to the AudioClip variable in the Waterfall Audio Source.
4. Enable **Loop** on the Audio Source so that the audio will repeat indefinitely.
5. Playtest the scene. You should hear the waterfall sound continuously.

**Key Points**:
- The sound will be 2D by default, so it doesn’t change based on your distance from the waterfall yet.
- We will adjust this in the next step.

---

### **3. Adjust the Audio Spatial Blend**

**Steps:**
1. Exit Play mode.
2. In the Inspector, set the **Spatial Blend** of the Audio Source to 3D. This allows the sound to adjust volume based on distance.
3. Adjust the **Minimum Distance** so the inner sphere is about the size of the cave opening.
4. Set the **Maximum Distance** to around 10 units.

**Test the Scene**: When you playtest again, notice how the volume of the waterfall changes as you move closer or farther from the sound source.

---

### **4. Adjust the Audio Spread**

**Steps:**
1. In Play mode, move near the edge of the Max Distance and turn left and right. Listen to how the sound is distributed across the speakers.
2. Adjust the **Spread** value to 180 to balance the sound in both speakers.
3. Find the Spread setting that sounds most natural to you, and remember the value.

**Key Concept**:
- A **Spread** of 180 ensures a more natural, immersive experience where the sound doesn’t “jump” between the left and right speakers.

---

### **5. Explore Logarithmic Rolloff**

**Steps:**
1. Set the **Max Distance** to 500 and observe the Logarithmic Rolloff graph.
2. Set the Max Distance back to 10 and observe the change in the graph.
3. Enter Play mode and test how long the waterfall is audible after moving away from it.

**Reflection**:
- Logarithmic Rolloff simulates how sounds fade over distance, and it’s great for large-scale audio like waterfalls.

---

### **6. Explore Linear Rolloff**

**Steps:**
1. Switch the **Volume Rolloff** from Logarithmic to Linear.
2. Playtest the scene. Notice how the sound fades out abruptly once the player exceeds the Max Distance.

**Reflection**:
- **Linear Rolloff** works well for drawing attention to specific objects but isn’t ideal for ambient sounds like waterfalls.

---

### **7. Create a Custom Rolloff**

**Steps:**
1. Change the **Volume Rolloff** to Custom.
2. Edit the volume curve. Move tangents and add points to make the curve behave as you want.
3. Playtest and fine-tune until you’re happy with the result.

**Key Goal**:
- Create a rolloff curve that fades the waterfall sound smoothly, with a natural rise and fall in volume.

---

### **8. Adjust the Audio Listener**

**Steps:**
1. Select the Main Camera in the Hierarchy and remove the **Audio Listener** component.
2. Attach the **Audio Listener** to the PlayerArmature instead of the camera.
3. Playtest the scene. Notice how the sound now follows the player character more naturally.

---

### **9. Experiment with the Doppler Effect**

**Steps:**
1. Explore the **Doppler Level** property in the Audio Source component.
2. Test the effect by moving the player character toward and away from a moving audio source.

**Reflection**:
- The **Doppler Effect** simulates pitch changes based on the relative speed of the listener and the sound source. Try to incorporate this into your scene!

---

### **10. Explore: Add More Ambient Audio**

**Next Step**:
- Consider adding additional sound effects to enhance the scene. Add three more ambient sound sources, such as birds or wind, and adjust their rolloff settings to match the environment.

---

**Congratulations!** You have successfully implemented and customized 3D sound effects in Unity! Keep experimenting to refine your understanding of audio design in game development.
