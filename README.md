# RoRD: Rotation-Robust Descriptors and Orthographic Views for Local Feature Matching  
#### [Udit Singh Parihar](https://www.linkedin.com/in/udit-singh-parihar-0bab24b7/)<sup>\*1</sup>, [Aniket Gujarathi](https://www.linkedin.com/in/aniket-gujarathi/?originalSubdomain=in)<sup>\*1</sup>, [Kinal Mehta](https://kinalmehta.github.io/)<sup>\*1</sup>, [Satyajit Tourani](https://scholar.google.com/citations?user=943lKscAAAAJ&hl=en)<sup>\*1</sup>, [Sourav Garg](https://www.linkedin.com/in/gargsourav/)<sup>2</sup>, [Michael Milford](https://www.linkedin.com/in/michaeljmilford/)<sup>2</sup> and [K. Madhava Krishna](https://robotics.iiit.ac.in/)<sup>1</sup>  


<sup>\*</sup> Denotes Equal Contribution  
<sup>1</sup> Robotics Research Center, IIIT Hyderabad.  
<sup>2</sup> QUT Centre for Robotics, Queensland University of Technology (QUT), Australia. 


> #### [Paper](https://arxiv.org/abs/2103.08573) | [Code](https://github.com/UditSinghParihar/RoRD)  
> Accepted to [IROS 2021](https://www.iros2021.org/)  


<!-- ![Alt Text](images/teaser.jpg) -->
<!-- <img src="images/teaser.jpg" alt="teaser" width="450"/> -->

<!-- <p align="center">
<img src="images/teaser.jpg" alt="teaser" width="450"/>
</p>
 -->
<img src="images/teaser2.jpg" alt="pipeline" width="1000" height="220" />  

**Local feature matches using RoRD**. Our method RoRD finds precise local feature correspondences under extreme viewpoint (180 degrees) changes for both indoor and outdoor sequences.  


<iframe width="560" height="315" src="https://www.youtube.com/embed/4n6_6TMnlOc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Abstract   
We present a novel framework that combines learning of invariant descriptors through data augmentation and orthographic viewpoint projection. We propose *rotation-robust* local descriptors, learnt through training data augmentation based on rotation homographies, and a *correspondence ensemble* technique that combines vanilla feature correspondences with those obtained through rotation-robust features. Using a range of benchmark datasets as well as contributing a new bespoke dataset for this research domain, we evaluate the effectiveness of the proposed approach on key tasks including pose estimation and visual place recognition.  


<!-- ![Alt Text](images/newPipeline3.jpg) -->
<img src="images/newPipeline3.jpg" alt="pipeline" width="1000" height="250" />

 **RoRD pipeline**. Our approach takes a pair of perspective view images with significant viewpoint as input to the Orthographic View Generator, which aligns the camera to the plane-surface-normal to generate the top views. These top views are then passed to an ensemble of *Vanilla D2-Net* and *RoRD* techniques (ours). This approach creates precise feature correspondences that are robust to variations in viewpoints.


## Dataset  
The DiverseView dataset consists of 4 scenes of indoor and outdoor locations, with images captured at high viewpoint changes and camera rotations (up to 180 degrees). For the data collection, we have used the Intel RealSense D455 camera with RGB, Depth, and IMU sensors.  

The three sequences of this dataset are as follows: 
1. *Sequence 1* consists of 1138 images of an office-desk scene captured by moving around it in a semi-circular path, thus exhibiting extreme rotation variations.   
2. Sequence 2 consists of 2534 images obtained from a 360 degrees traversal about a table-top.   
3. *Sequence 3* consists of 1519 images facing a wall with high viewpoint changes but limited camera rotations.   
4. *Sequence 4* consists of 3931 images captured around a building with graffiti-art with varied camera viewpoints and rotations in low-lighting dusk conditions.  


## Results  
<p align="center">
<img src="images/results_qual.jpg" alt="results" width="800"/>
</p> 

**Qualitative results from the DiverseView dataset**. Each row corresponds to a different sequence from the dataset. *RoRD* leverages its learnt *rotation-robust features* to obtain precise feature correspondences, outperforming D2-net. Incorporating orthographic views with RoRD, *(RoRD + OV)* further improves performance, and outperforms both D2-Net and RoRD for all the four sequences.  


<p align="center">
<img src="images/hseq.png" alt="results" width="400"/>
<img src="images/hseq_rotated.png" alt="results" width="400"/>
</p> 

**MMA results on standard and proposed HPatches variant.** 