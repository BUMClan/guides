# HALO DART configuration

In order to make a DART (Disable Alpha Rendering Targets) configuration, you have to adjust the file **config.txt** in your HALO installation folder.

You have to find the right graphic card section and add ```DisableAlphaRenderTargets``` to it.

## Example
<pre>
...
0x0338 = "GeForceFX 3000"
Unknown = "Unknown"
	UseAnisotropicFilter
	if os < Win2K
		if driver < 4.14.10.4467
			LinearTextureAddressing
		endif
		if driver < 4.13.01.4071
			OldDriver
		endif
		if driver == 4.14.10.4524
			LinearTextureAddressingZoom
			LinearTextureAddressingSun
		endif
	endif
	if os == Win2K
		if driver < 6.14.10.4467
			LinearTextureAddressing
		endif
		if driver < 6.13.10.4071
			OldDriver
		endif
		if driver == 6.14.10.4524
			LinearTextureAddressingZoom
			LinearTextureAddressingSun
		endif
	endif
	if os > Win2K
		if driver < 6.14.10.4467
			LinearTextureAddressing
		endif
		if driver < 6.13.10.4071
			OldDriver
		endif
		if driver == 6.14.10.4524
			LinearTextureAddressingZoom
			LinearTextureAddressingSun
		endif
	endif
	<b>DisableAlphaRenderTargets</b>
	break
	...
</pre>

The above example adds the DART configuration for a NVIDIA card with unknown type, so the section ```Unknown = "Unknown"``` must be used and only a ```break```command prevents HALO for looking up further grahic cards. In this case, it is the last configuration for NVIDIA cards and therefore, the lookup wouldn't continue anyway.

If your graphic card would be e.g. a "NVIDIA GeForce4 MX 460", you would adjust the following corresponding section like this:
<pre>
...
0x0170 = "GeForce4 MX 460"
	<b>DisableAlphaRenderTargets</b>
	break
...
</pre>


---
Version: 1.0<br>
Date: May 15, 2024
