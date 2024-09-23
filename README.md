# PMDG_777X_SDK Class
This file can be inserted into an MSFS managed code (C#) project to implement the PMDG 777X SDK.
It is somehow the alter ego of the <PMDG_777X_SDK.h> file used in unmanaged (C++) code, and marshals its non-blittable fields.

PMDG is providing the <PMDG_777X_SDK.h> header file for unmanaged code as part of the airplane documentation, but not for managed code.
Besides, I could not find this managed code 777X SDK file in GitHub or elsewhere.
That's why I decided to create it and share it.
I'm currently using it for an MSFS PMDG 777-300ER client project I created, and it seems to be working as expected as is.

One thing to notice is that for the CDU Cell structure, the 'Symbol' must be marshalled as 'public byte' for WPF code, otherwise some CDU characters will not be recognized.
The issue affects the following characters (as far as I have noticed):
- Degree sign.
- Vertical empty rectangles.
- Left and right arrows.
- 
I guess this has something to do with the used Font but I'm still trying to find out. Oddly, Windows Forms projects are not affected by this unknown character issue.
However, the Unicode value of the above mentioned characters must be modified to draw the correct symbols in WPF and in Windows Forms.

Any comment or suggestion for improvement or editing would be welcome.
leo-us@orange.fr
