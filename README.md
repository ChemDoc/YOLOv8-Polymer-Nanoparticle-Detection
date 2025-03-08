# YOLOv8-Polymer-Nanoparticle-Detection
This project applies YOLOv8 for the detection and morphological analysis of polymer nanoparticles observed via Transmission Electron Microscopy (TEM). The goal is to classify different nanostructures and measure their dimensions based on a scale bar for accurate size conversion.

 1-Detected Nanoparticle Types:
Based on the study "Multicompartment Vesicles: A Key Intermediate Structure in Polymerization-Induced Self-Assembly of Graft Copolymers," we classify and detect the following morphologies:
  LCN (Large Compound Nano-object): Formed by fusion of Multicompartment Vesicles (MCV), appearing as spherical or cylindrical objects.
  MCV (Multicompartment Vesicle): Intermediate structures containing multiple hydrophilic cores within a membrane, attributed to phase separation of dextran and residual monomer.
  TMCV (Thick Membrane Multicompartment Vesicle): A transitional form of MCVs with a thicker membrane before merging into LCNs.
  V (Unilamellar Vesicle, ULV): Formed at a lower polymerization degree (X = 100), these single-layer vesicles are thinner but grow progressively.
  Scale Bar: A detected reference scale to convert pixel measurements into nanometers, set at 200 nm.

2-Prediction Process
The program utilizes three different YOLOv8 models (YOLOv8n, YOLOv8s, and YOLOv8m) to perform multi-scale detection of nanoparticles. The models process the input TEM images separately, and their predictions are merged using a weighted box fusion (WBF) technique. This improves detection accuracy and reduces false positives.
After detection, the bounding boxes are converted from pixels to nanometers based on the scale bar, allowing precise size measurements and statistical analysis of nanoparticle distribution.

3-Dataset Availability:
The annotated TEM images and training code are available on Zenodo.

4- The models were trained using the following hardware and software setup:
CPU: Intel Core(TM) i7-1068NG7 2.30GHz
OS: Ubuntu 20.04
Python Version: 3.12.9
Torch Version: 2.2.2 (CPU)
Framework: PyTorch 2.0 + Ultralytics YOLOv8
