**********************************************************************
**
**	TratamientoImagen: hyperspectral image processing software
**	Grupo Orión, Universidad de Extremadura	
**	Orion research group, University of Extremadura
**	
**	Authors: C. Caruncho, P.J. Pardo, H. Cwierz
**	
**********************************************************************

==================================================
1. Prerequisites for Deployment 
==================================================

Verify that MATLAB Runtime(R2023a) is installed.   
If not, download and install MATLAB Runtime for R2023a from the following link on the MathWorks website: https://www.mathworks.com/products/compiler/mcr/index.html

==================================================
2. Files needed for proper execution and operation
==================================================

- TratamientoImagen.exe (you can download it from the "Releases" section on the right side of this repository)
- This readme file 

Image processing:

- 6 Hyperspectral ENVI files: raw, whiteReference and darkReference (data and header for each one of them)
- Illuminant (*.mat): D50, D60... your choice
- Calibration White reference (*.mat): MatLab file for adjusting the white calibration, since the reflectance of the target device can be damaged over time.
- Standard Observer (*.txt): response of the standard observer to light, containing the wavelengths and the corresponding color matching functions (X, Y, Z)

You need to provide at least the 6 hyperspectral files, generated with a hyperspectral camera.
As an example, we provide the rest of the files, but you can, of course, use your own.

==================================================
3. Software operation
==================================================

We advice you to create a folder and place all the files in it. Group the ENVI files in a subfolder, where all the files generated during processing will be stored.

Double click on the TratamientoImagen.exe icon and MATLAB Runtime(R2023a) will compile and execute it. A window will open, with two panels:
	
- Files panel: you need to provide the appropriate information for each file
   1. Main folder name: click the "Browse" button and select the subfolder containing raw and white/dark reference ENVI files
      Important: If your files are named differently, rename them to: raw, whiteReference and darkReference. Do NOT change the extension "hdr" of the header files.
   2. Standard observer: click the "Browse" button and select the text file containing the CIE description of the 2º observer
   3. Light source file: click the "Browse" button and select the MatLab file containing the power spectral density of the light source used when the hyperspectral photograph was taken
   4. White reference: click the "Browse" button and select the white calibration MatLab file, describing the target device

- Image processing panel: 
   1. Deploy menu "pieces": specify the number of pieces in which the file will be divided.
   2. Deploy menu "Color space": choose the color conversion matrix you want to use.
   3. Wavelengths span: select the starting and ending wavelengths that you want to process, along with the desired step between them.
   4. Options: you can check the boxes to activate the following options
      - gamma correction: adjustment applied to the colors to compensate for the non-linear response of human vision 
      - generate one bmp per frame: the software generates automatically one binary file per frame, but if you want to see the frames, bmp files are needed
      - show final image: at the end of the image processing, the software will automatically open the hyperspectral image for you to see
   5. Run buttons: 
      - start processing: run the software and process the raw hyperspectral data
      - inspect reflectances: once the raw data are processed, you can visually inspect the hyperspectral image pixel-by-pixel 
		



