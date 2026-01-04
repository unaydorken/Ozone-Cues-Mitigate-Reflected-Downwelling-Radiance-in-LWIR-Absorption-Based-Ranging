# Ozone Cues Mitigate Reflected Downwelling Radiance in LWIR Absorption-Based Ranging
Passive long-wave infrared (LWIR) absorption-based ranging estimates object distance by exploiting wavelength-dependent atmospheric absorption in emitted thermal radiation. Unlike active depth sensing, this approach operates day and night without external illumination and does not rely on scene texture.
In natural scenes with low temperature contrast, however, reflected thermal radiation—particularly downwelling radiance from the sky—can significantly distort absorption features and lead to large range overestimation, especially for reflective materials.

This paper identifies reflected downwelling radiance as a primary source of error in absorption-based ranging and introduces a principled way to mitigate its effects using ozone absorption cues.
While most LWIR absorption features arise from water vapor and affect both ground-level propagation and downwelling radiance, the ozone absorption band near 9.5 µm provides a distinctive spectral signature that is unique to downwelling radiance.
This enables separation of emitted and reflected components in the observed radiance.

We propose two new ranging methods that exploit this insight. The quadspectral method uses four narrow spectral bands—two near water vapor absorption and two near ozone absorption—to obtain a simple closed-form range estimate with minimal computation.
The hyperspectral method leverages a broader spectral range to improve robustness under low temperature contrast while jointly estimating range, object temperature, emissivity profiles, and reflected downwelling contributions.

Experimental results on real LWIR data demonstrate substantial improvements in ranging accuracy. In challenging scenes where neglecting reflected downwelling radiance leads to large range overestimation, the proposed methods significantly reduce error, with the hyperspectral approach achieving meter-level accuracy.

## Example Result: Effect of Downwelling Radiance

<p align="center">
  <img src="Figures/RGB_photo.png" width="32%">
  <img src="Figures/introduction_hyperspectral_no_downwelling_range.png" width="32%">
  <img src="Figures/introduction_hyperspectral_with_downwelling_range.png" width="32%">
</p>

<p align="center">
  <em>
  Left: RGB photograph (reference only).  
  Middle: Absorption-based ranging when downwelling radiance is neglected
  (reflective surfaces are overestimated).  
  Right: Ranging results when reflected downwelling radiance is accounted for.
  </em>
</p>

<p align="center">
  <img src="Figures/introduction_hyperspectral_spectral_signatures.png" width="85%">
</p>

<p align="center">
  <em>
  Spectral measurements at a reflective panel, grass area, and sky pixel.
  The ozone absorption band provides a distinctive cue for identifying
  reflected downwelling radiance.
  </em>
</p>
