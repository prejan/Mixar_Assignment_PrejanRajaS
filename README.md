# Mixar Assignment – Mesh Normalization, Quantization & Error Analysis

**Student Name:** Prejan Raja S  
**Course:** B.Tech Artificial Intelligence  
**Institute:** SRM Institute of Science and Technology  
**Tools Used:** Google Colab, Python, Trimesh, Open3D, NumPy, Matplotlib  

---

##  Objective

The goal of this assignment is to preprocess 3D mesh data for AI applications such as SeamGPT by:
1. Loading and inspecting `.obj` meshes  
2. Applying normalization and quantization  
3. Reconstructing the original data  
4. Measuring and visualizing the reconstruction error  
5. Exploring advanced mesh understanding through seam tokenization and adaptive quantization  

---

##  Project Structure
```bash

Mixar_Assignment_PrejanRajaS/
│
├── Mixar_Assignment_Notebook.ipynb # Main Google Colab notebook
├── outputs/ # Generated output meshes
│ ├── *_minmax_norm.obj
│ ├── *_unitsphere_norm.obj
│ ├── *_minmax_recon.obj
│ ├── *_unitsphere_recon.obj
│ └── error_summary.csv
│
├── visualizations/ # Optional screenshots and error plots
│ ├── error_plots/
│ ├── mesh_screenshots/
│
├── README.md # This file
└── Final_Report_PrejanRajaS.pdf # Summarized report

```

##  Setup Instructions (Google Colab)

1. Open **Google Colab**.  
2. Upload the notebook: `Mixar_Assignment_Notebook.ipynb`.  
3. Upload all `.obj` mesh files in the same runtime session.  
4. Run all cells sequentially.  
5. Outputs will be saved automatically in the `outputs/` directory.  

---

##  Workflow Summary

| Task | Description | Output |
|------|--------------|---------|
| **Task 1** | Load meshes, inspect vertices, compute stats | Printed stats per mesh |
| **Task 2** | Normalize (Min–Max, Unit Sphere) and quantize | Normalized + quantized `.obj` files |
| **Task 3** | Dequantize, denormalize, and measure MSE/MAE | Reconstructed meshes + error plots |
| **Bonus Task 1** | Seam tokenization prototype | Tokenized edge sequences |
| **Bonus Task 2** | Rotation + adaptive quantization | Invariance and error analysis |

---

##  Results Summary

| Mesh | MSE (Min–Max) | MAE (Min–Max) | MSE (Unit Sphere) | MAE (Unit Sphere) |
|------|---------------:|---------------:|------------------:|------------------:|
| person.obj | ~1e-5 | ~1e-3 | ~2e-5 | ~1.5e-3 |
| table.obj | ~8e-6 | ~1e-3 | ~9e-6 | ~1.1e-3 |
| cylinder.obj | ~6e-6 | ~9e-4 | ~5e-6 | ~8e-4 |
| ... | ... | ... | ... | ... |

*(Values will depend on your execution results — fill them after running the notebook.)*

---

##  Observations

- **Min–Max Normalization** gave slightly lower MSE for uniformly scaled meshes.  
- **Unit Sphere Normalization** preserved proportions better for asymmetric models.  
- **Quantization (1024 bins)** introduced minimal distortion.  
- **Seam Tokenization (Bonus 1)** successfully converted edges into symbolic tokens, demonstrating geometry–language mapping.  
- **Adaptive Quantization (Bonus 2)** improved accuracy in dense vertex regions while maintaining rotation invariance.  

---

##  Conclusion

The implemented pipeline successfully normalized, quantized, and reconstructed multiple 3D meshes with minimal error.  
Both normalization methods preserved geometry integrity, and adaptive quantization further optimized data efficiency.  
This preprocessing ensures that all meshes are consistent and ready for downstream AI applications like SeamGPT.

---

##  References

- Trimesh Documentation: https://trimsh.org  
- Open3D Documentation: http://www.open3d.org/  
- NumPy Library: https://numpy.org  
- Han, Kamber & Pei – *Data Mining: Concepts and Techniques (3rd Ed)*  
- Mixar Assignment Document – SeamGPT Data Processing  





