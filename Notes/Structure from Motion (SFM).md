Tags: #perception-3d 

Pages [[poly_perception_3d.pdf#page=11|11]] à [[poly_perception_3d.pdf#page=23|23]]
## Basic concept

Structure from Motion (SfM) is a technique used in computer vision and photogrammetry to reconstruct the 3D structure of a scene or object from a collection of 2D images or video frames. It's a fundamental component in 3D perception and plays a crucial role in various applications such as robotics, augmented reality, virtual reality, geographic information systems (GIS), and more.

Here's a breakdown of the key aspects and components of SfM in 3D perception:

1. **Image Collection:**
   SfM starts with capturing a set of images of a scene or object using cameras from different viewpoints. These images serve as the input data for the reconstruction process.

2. **Feature Extraction:**
   In each image, distinctive features (e.g., keypoints, edges) are extracted. These features are identifiable and can be tracked across multiple images, serving as the basis for establishing correspondences.

3. **Feature Matching:**
   Correspondences between features in different images are established by matching the extracted features. This step is critical for determining how the features in one image relate to those in another.

4. **Camera Pose Estimation:**
   Given the correspondences between features, SfM algorithms estimate the camera poses (positions and orientations) for each image. This step involves determining the position and orientation of each camera relative to a common coordinate system.

5. **Sparse Point Cloud Reconstruction:**
   Based on the camera poses and feature correspondences, SfM algorithms generate a sparse 3D point cloud representing the positions of features in the scene. This point cloud is an initial estimation of the scene's 3D structure.

6. **Bundle Adjustment:**
   Bundle adjustment is an optimization step that refines the camera poses and 3D point positions to minimize the reprojection error. It optimizes the positions of cameras and 3D points to ensure the reconstructed scene aligns well with the actual images.

7. **Dense Reconstruction (Optional):**
   In some cases, additional steps may be taken to generate a dense 3D reconstruction by estimating the depth or surface geometry at each pixel in the images.

8. **Meshing and Texturing:**
   The 3D point cloud or dense reconstruction can be further processed to create a mesh representing the surface geometry of the scene. Texture can be mapped onto this mesh using the original images.

9. **Output and Visualization:**
   The final 3D model, typically represented as a mesh or point cloud, can be visualized and used for various applications such as virtual reality, 3D modeling, simulation, or analysis.

SfM is a fundamental step in many applications that require 3D understanding of a scene from 2D images, and it's often used in conjunction with other techniques like Simultaneous Localization and Mapping (SLAM) for real-time 3D reconstruction in dynamic environments.

## Approche globale

The global approach in Structure from Motion (SfM) aims to simultaneously estimate the 3D structure (e.g., 3D points representing the scene) and camera poses (positions and orientations of cameras) for all images in the collection, considering the entire set of images as a whole. It involves solving a large optimization problem to achieve a globally consistent reconstruction.

![[Pasted image 20230919144738.png]]



## Approche incrémentale

On commence avec une reconstruction sur 2 vues, puis on enrichie avec d'autres vues / points 3D

Je prends deux vues qui ont un max de points en commun

A partir de la je reconstruit les params extrinsèques