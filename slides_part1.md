50

when talking about an object's SPD, we are indeed referring to how much light (radiant energy) is reflected at different wavelengths of light. 

Illuminants (the light sources) have their own SPD, which can change the color appearance of an object. For example, the same tomato will appear different under various lighting conditions because the SPD of the illuminant affects what wavelengths are reflected.
___
52

The barn appears in two lighting conditions: one side of the image is cooler (bluish), while the other side is warmer (yellowish). Chromatic adaptation allows us to perceive both sides as consistent in color, despite the different lighting conditions.

___
54


Image sensors, like those in cameras, do not have the same adaptation capability. This is why cameras rely on a white-balance module, which tries to replicate color constancy by adjusting the image based on the light source. This will be discussed in more detail in "part 2."

___
55

The Von Kries Transform mathematically compensates for different lighting conditions by normalizing the responses of the L/M/S cones based on the light source. This transform helps maintain color constancy by adjusting colors in a scene to appear consistent under various lighting conditions.



___

59

Color temperature is a way to describe the color of light emitted by an illuminant, expressed in Kelvin (K). It is widely used in photography and display industries to characterize the color of illumination.
 
A higher color temperature (e.g., 6500K) corresponds to bluer (cooler) light, while a lower color temperature (e.g., 2700K) corresponds to yellower (warmer) light.


Cameras use color temperature (often in the form of white balance settings) to adjust for the lighting in a scene, ensuring that colors appear accurate regardless of the illumination. By calibrating the camera based on the light's color temperature, the camera can correct the image so that white objects appear white under various lighting conditions.

Correlated Color Temperature (CCT) refers to the temperature of a theoretical blackbody radiator that produces light of similar color to the illuminant. It is an approximation of how warm or cool a light source appears.


A metamer is a phenomenon where two different spectral power distributions (SPDs) appear as the same color to the human eye. This is important in color constancy and white balance, as different light sources can have different SPDs but still produce the same perceived color.
    
Example: Two light sources (e.g., sunlight and certain LEDs) may have completely different SPDs, but under each, a white piece of paper might appear the same color due to metamerism.

___
60

Right graph: Shows the SPDs of different artificial light sources like metal halide, fluorescent, and daylight fluorescent bulbs.These sources exhibit sharp peaks and valleys because they emit light at specific wavelengths rather than across a continuous spectrum like natural sunlight.

___
61
The CIE Standard Illuminants represent various standard light sources used for color calibration in imaging and photography. Each graph shows the SPD for different standard illuminants

___
62

1.  **Color Temperature**:
    
    -   This refers to the temperature of a theoretical blackbody radiator that emits light of a similar color to a given light source. It is used to describe the appearance of a light source in terms of warmth or coolness.
    -   For example, daylight is approximately 6500K, while incandescent light might be around 2700K.
2.  **Blackbody Radiation**:
    
    -   A blackbody is an idealized physical object that absorbs all incident radiation and emits radiation based on its temperature. The spectrum of emitted light is determined by Planck’s Law, which relates the spectral density of electromagnetic radiation to the temperature T of the blackbody.
    
    The formula:
    
    $$B(\lambda, T) = \frac{2hc^2}{\lambda^5} \cdot \frac{1}{e^{\frac{hc}{\lambda k_B T}} - 1}$$
    -   **$B(\lambda, T)$**: Spectral radiance at wavelength λ\lambdaλ and temperature $T$.
    -   **$h$**: Planck's constant.
    -   **$c$**: Speed of light.
    -   **$k_B$​**: Boltzmann constant.
    -   This formula describes how the intensity of emitted radiation varies with wavelength for a given temperature.


If you're setting up a studio for a photoshoot and want a natural daylight feel, you'd choose lights with a CCT of around **5500K-6000K** (daylight). If you're designing a living room, you'd choose lighting around **2700K** to create a warm and inviting atmosphere similar to an incandescent bulb.


The graph shown in the slide represents blackbody radiation, which is the theoretical spectrum of light emitted by a perfect blackbody at different temperatures. The blackbody is an idealized object that absorbs all incoming radiation and re-emits it based on its temperature. The graph follows Planck’s Law, which defines the spectral distribution of the radiation emitted by a blackbody.

X-Axis: Wavelength (λ) in micrometers (μm)
The x-axis represents the wavelength of the emitted radiation, typically measured in micrometers (μm).
Shorter wavelengths are toward the left (e.g., blue/violet light), and longer wavelengths are toward the right (e.g., red light and beyond into infrared).
Y-Axis: Spectral Radiance (Intensity)
The y-axis represents the intensity or the radiant energy emitted per unit surface area per unit wavelength at a given temperature.
This axis shows how much energy is emitted at each specific wavelength.
Key Takeaways from the Graph:
As the temperature increases, the peak of the curve shifts toward shorter wavelengths (higher energy light). For instance, a higher temperature (e.g., 6000K) emits more blueish light, while a lower temperature (e.g., 4000K) emits more reddish light.
Each curve corresponds to a specific temperature (e.g., 3000K, 5000K, 6000K), and the shape of the curve shows how much light is emitted at different wavelengths for that temperature.
Explanation of the Curve Shapes:
At lower temperatures (like 4000K), the majority of radiation is emitted at longer wavelengths, giving the object a reddish or yellowish color.
At higher temperatures (like 6000K), more radiation is emitted at shorter wavelengths, resulting in a bluish light.
In the graph shown in the slide:

The curve for 6000K peaks around the blue part of the spectrum (shorter wavelengths).
The curve for 4000K peaks more toward the red part of the spectrum (longer wavelengths).
How It Relates to Color Temperature:
The graph illustrates how different blackbody radiators at various temperatures emit light of different colors. This relationship helps us understand color temperature—for instance, why a 6000K light source appears blue and a 3000K light source appears red or orange.

___
63

The right figure is showing that at lower temperatures like 1000K, most of the radiation is in the infrared, which we cannot see. As the temperature increases, more of the radiation moves into the visible spectrum.
___
64

Planckian Locus: The black curve running through the diagram shows where various blackbody radiators fall in terms of their chromaticity as temperature changes (in Kelvin). Each point on the curve corresponds to the color of light emitted by a blackbody at a specific temperature.

Color Temperature Mapping: The diagram links the color temperature of light sources (in Kelvin) to their CIE chromaticity coordinates. For example, a light source with a temperature of 3000K will appear warmer (more red/yellow), while one with 6000K will appear cooler (more blue/white).
___
66
A blackbody is an idealized physical object that perfectly absorbs all incident electromagnetic radiation, regardless of frequency or angle of incidence. It also emits radiation in a characteristic way that depends only on its temperature. This radiation emitted by a blackbody is called blackbody radiation.

___
68
A white point in color science refers to a specific reference point on the CIE chromaticity diagram (shown in the image) that we want to consider as "white" under a specific light source or illuminant. It's a reference for neutrality, often used in calibrating displays and photography to ensure accurate color representation.

D65 is commonly used as a reference white in many colorimetric standards and represents average daylight.
___
72
RGB Primaries: RGB dominates in industries such as lighting (LEDs), monitors (CRT, LCD), etc. because we can physically produce red, green, and blue light sources.
___
73

A color space is a specific range of colors that a device (like a monitor, camera, or printer) can display or capture. It defines how colors map onto the device, including the limits of the colors it can produce.

The white point is a specific point in the color space that defines what the device considers "white" under certain lighting conditions.

The white point ensures that no matter what light is present in the environment, the device will try to render white as consistently as possible. 

For each light source with a different color temperature (e.g., warm, cool, or neutral), the white point will shift to compensate for the color cast of that light. 

Color Model (Framework)
A color model is a mathematical system that describes how to represent colors using numbers. It provides the structure for how colors are arranged, but it doesn’t specify exactly which colors should be included. Think of it as a blueprint, but it’s not tied to any specific physical or digital device.

Examples of Color Models:
RGB (Red, Green, Blue): Colors are described by combining red, green, and blue light. Each color is defined as a combination of these three values.
HSV (Hue, Saturation, Value): Colors are described by their hue (the type of color), saturation (intensity of the color), and value (brightness).
HSL (Hue, Saturation, Lightness): Similar to HSV, but instead of “Value,” it uses "Lightness."
The color model provides the framework for how colors can be defined, but doesn’t specify exactly which shades of red, green, or blue should be used.

Color Space (Specific Set of Colors)
A color space is a specific range of colors that a device (like a monitor or printer) can display, within a particular color model. It’s like choosing a subset of colors from a color model and mapping them to a real-world system.

The color space defines which specific red, green, and blue tones should be used in an RGB model.
Different color spaces allow devices to display or print colors differently depending on their capabilities.
Example of a Color Space:
sRGB (standard Red Green Blue): This is a color space that defines the specific shades of red, green, and blue for the RGB model, commonly used in monitors, printers, and the web.
AdobeRGB: Another color space for the RGB model, but it allows for a wider range of colors (a bigger gamut) than sRGB, making it popular in professional photography and design.
So while RGB is the model (the general idea of combining red, green, and blue), sRGB and AdobeRGB are spaces that define which specific shades of red, green, and blue should be used in real-world applications.
___
75

Why RGB is Not Enough: Different devices can use slightly different definitions of "red," "green," and "blue," leading to issues with color consistency when transferring images between devices (e.g., from a monitor to a phone).
Key Issue: If the RGB values are not specified carefully, color reproduction can vary widely between devices.
The image illustrates:

Multiple RGB gamuts (RGB 1, 2, 3) plotted on the CIE xy chromaticity diagram. It shows that different definitions of "RGB" can cover different areas of the color space, meaning that different devices might display the same RGB value differently.
The key takeaway is that while we use RGB as a standard for color representation, it must be tied to specific color spaces (like CIE XYZ) to ensure accurate color reproduction across different devices.

___
77
sRGB White Point: sRGB assumes a D65 (6500K daylight) white point. Viewing the same content under different lighting (like D50) changes how the colors appear, because your eyes adapt to the surrounding light.

This slide explains how white points in color spaces relate to how displays show colors. For sRGB, the white point corresponds to D65, but other white points, like D50 (5000K), are used in some environments.

When a display is viewed under different lighting conditions, such as D50 (5000K), the eye adapts to the environment’s light. This adaptation may make the colors appear different.
The two boxes with D50 and D65 show how displays look under different lighting conditions. For instance, if a display is optimized for D65 but viewed under D50 lighting, your eyes adapt to the different illumination, affecting your perception of color.

___
79
CIE XYZ is a color space that represents human vision in a very broad and uniform way. It was designed to be a device-independent color space, meaning that it's not tied to any specific display or device. When you convert color values from the CIE XYZ space to sRGB, you're transforming from a broad, universal color representation to a color space optimized for digital displays like monitors and TVs.
sRGB is a standard color space for devices like cameras, printers, and displays, and it is designed to approximate the colors that humans can see in typical daylight conditions.
___
80

Gamma correction is applied as part of the process to map linear light intensity (how much physical light is emitted) to how we perceive brightness. Human eyes do not perceive brightness linearly. For example, doubling the intensity of a light source does not result in us perceiving it as twice as bright.
Without gamma correction, the images displayed on devices would look too dark or too bright in certain areas because our eyes are more sensitive to changes in darker tones than in lighter ones.
How Gamma Correction is Used in sRGB:
sRGB applies gamma correction to match the nonlinear way humans perceive brightness. The sRGB gamma curve (as shown in the diagram) ensures that darker colors get more bits in a digital image, while brighter colors get fewer bits. This compensates for the fact that we are more sensitive to changes in darker areas.


-   The gamma correction equation you saw,$I' = 255 \times I^{1/2.2}$, adjusts the input (linear light intensity) so that the output looks more natural to human eyes.
CIE XYZ is a broader, device-independent color space, and when converting to sRGB, a matrix conversion is done first to map the colors from one space to another.
Gamma correction is then applied to the resulting sRGB values to ensure that the brightness levels match human perception when displayed on a device.
Gamma correction doesn’t specifically apply to CIE XYZ but is critical in the final step when displaying colors on a screen using sRGB values.
In other words, gamma correction is part of the process to ensure that colors displayed in sRGB match how humans perceive brightness, and it’s applied after transforming color values from CIE XYZ.

___
81

This curve shows that as the stimulus increases, human perception increases more slowly. In the graph, it shows that even if the radiometric power (brightness) increases linearly, the perceived brightness follows a curve.

___
83

Perceptual Encoding: The last image ties gamma correction back to human vision, stating that sRGB gamma correction approximates Stevens' power law. This means that sRGB uses gamma encoding to match how we perceive brightness changes.
The reason for applying gamma correction is not to compensate for a display technology (like CRTs), but to ensure that the digital values are perceptually uniform to the way humans experience brightness.
