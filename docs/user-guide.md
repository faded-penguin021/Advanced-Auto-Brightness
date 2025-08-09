---
layout: default
---

<div class="aab-user-guide">
<div class="banner">
    <h1>Advanced Auto Brightness</h1>
  </div>
  
  <div class="content-wrapper">
    <h3>Welcome to Advanced Auto Brightness</h3>
    <p>This project is a complete replacement for your phone's built-in auto brightness. Its goal is to provide a smoother, more intelligent, and completely customizable experience that adapts to light the way you want it to.</p>

    <hr>

    <h4>1. Getting Started: Two-Step Activation</h4>
    <p>Setting up is simple. There are only two things you need to do to get started.</p>
    <ol>
      <li><strong>Activate the Service:</strong> In the <strong>General</strong> tab, flip the master switch on the top right. A persistent notification will appear, confirming that AAB is active. This action also automatically disables Android's native auto brightness system.</li>
      <li><strong>Set Your Boundaries:</strong> Go to the <strong>Misc</strong> tab. Adjust the <strong>Min Brightness</strong> and <strong>Max Brightness</strong> sliders. This defines the absolute darkest and brightest your screen will ever get.</li>
    </ol>
    <div class="tip">
      <strong>Tip:</strong> For phones with OLED screens, setting <code>Min Brightness</code> to a small value like 5 or 10 instead of 0 can prevent "black crush" (loss of detail in dark areas).
    </div>

    <hr>

    <h4>2. Understanding the Control Panel</h4>
    <p>The settings are organized into three main tabs, each with a specific purpose:</p>
    <ul>
      <li><strong>General:</strong> This tab defines the <strong>shape</strong> of your brightness curve. It answers the question: "<em>What</em> brightness level should I have for <em>this</em> amount of ambient light?"</li>
      <li><strong>Reactivity:</strong> This tab controls the <strong>behavior</strong> of the sensor. It answers the question: "<em>When</em> should I react to a change in light, and how sensitive should I be?"</li>
      <li><strong>Misc:</strong> This tab sets the <strong>rules and feel</strong> of the system. Here you'll find the master brightness limits, animation controls, and global fine-tuning adjustments.</li>
    </ul>

    <hr>

    <h4>3. Tuning Your Brightness Curve (General Tab)</h4>
    <p>This is where you design your core brightness response. The system uses a sophisticated three-part formula to give you precise control where it matters most.</p>
    <ul>
      <li><strong>Zone 1 (Darkness to Dim Light):</strong>
        <ul>
          <li><code>Zone 1 Scaling</code>: This is your main control for low-light environments. Increase it to make the screen get brighter faster in the dark.</li>
          <li><code>Zone 1 End</code>: This sets the lux level where "dark" ends and "dim light" begins.</li>
        </ul>
      </li>
      <li><strong>Zone 2 (Dim to Medium Light):</strong>
        <ul>
          <li><code>Zone 2 Scaling</code> & <code>Offset</code>: These two work together to shape the curve for the most common indoor light levels. Adjust them and use the graph to see how they affect the transition from dark to dim.</li>
        </ul>
      </li>
       <li><strong>Zone 3 (Bright Light):</strong>
        <ul>
          <li>This zone is handled <strong>automatically</strong> by a formula that smoothly approaches maximum brightness. This prevents the screen from becoming blindingly bright too quickly when you step outside.</li>
        </ul>
      </li>
    </ul>
    
    <hr>

    <h4>4. Eliminating Flicker (Reactivity Tab)</h4>
    <p>A common issue with auto-brightness is jitter, annoying brightness fluctuations from minor sensor noise. This tab lets you eliminate it by creating a smart dead zone. The screen will only react when the light change is significant.</p>
    <ul>
      <li><strong>The Thresholds:</strong> <code>Dark</code>, <code>Dim</code>, and <code>Bright Threshold</code> control the size of this dead zone (as a percentage) for different light levels. Higher values mean more stability but less responsiveness.</li>
      <li><strong>The Curve:</strong> <code>Curve Mid</code> and <code>Slope</code> control how the dead zone smoothly transitions between the <code>Dim</code> and <code>Bright Threshold</code>threshold values you set.</li>
    </ul>

    <div class="tip">
      <strong>Your Secret Weapon:</strong> Long-press any setting's label in any tab to see a detailed tooltip explaining exactly what it does!
    </div>

    <hr>

    <h4>5. Visualize Before You Apply: Use the Graphs!</h4>
    <p>Don't guess what your changes are doing. AAB provides real-time graphs to show you the exact impact of your settings before you save them.</p>
    <ul>
      <li><strong>Brightness Graph (General Tab):</strong> The <strong>Teal Line</strong> is your custom curve. The <strong>Yellow Line</strong> is a reference. Adjust your settings until the teal line matches your preference.</li>
      <li><strong>Reactivity Graph (Reactivity Tab):</strong> This visualizes your dead zone curve. It shows you how stable the system will be at different light levels.</li>
    </ul>
    
    <hr>

    <h4>6. Saving Your Work</h4>
    <p>Your adjustments are temporary until you save them.</p>
    <ul>
      <li><code>Save & Apply</code>: Saves your changes and immediately applies them.</li>
      <li><code>Reset tab defaults</code>: Reverts the settings on the current tab to their original values.</li>
      <li><code>Exit</code>: Closes the control panel without saving any changes you've made.</li>
    </ul>

    <p>Enjoy your new intelligent auto brightness!</p>
  </div>
</div>
