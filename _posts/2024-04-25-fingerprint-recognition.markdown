---
layout: post
title:  "Fingerprint features"
date:   2024-04-25 14:30:30 +0800
categories: jekyll update
---
Local Structure in Fingerprints

The local structure in fingerprints refers to the detailed features within the fingerprint patterns, such as local ridge orientations, bifurcations (where a ridge splits), and ridge endings (where a ridge stops). These features are crucial for fingerprint identification as they are unique to each individual. Typically, acquiring the local structure of a fingerprint involves image processing techniques such as enhancement, binarization, and thinning, followed by the extraction of minutiae points based on these detailed ridge patterns.
![Image name](/images/local_structure.png)

Draw Minutiae in Fingerprints
Drawing minutiae involves visually representing the critical points of a fingerprint, primarily the ridge bifurcations and endings. This process is essential in fingerprint analysis and identification systems. To draw minutiae, the fingerprint image is first processed to clarify and emphasize the ridge patterns. Techniques such as ridge filtering and skeletonization may be used to refine the image. Once the minutiae points are identified, they can be marked on the fingerprint image, often highlighted with different symbols or colors to distinguish between types of minutiae (e.g., ending as a dot, bifurcation as a branch). This visual representation helps in comparing fingerprints and is used in various applications like forensic analysis and biometric authentication.
![Image name](/images/draw_minutus.png)

With the two features here, we can use them to compare fingerprints.
