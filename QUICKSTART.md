# Quick Start Guide

Get up and running with Palette Face Inpainting in 5 minutes!

## 🚀 Fastest Way: Kaggle (Recommended)

### Step 1: Upload to Kaggle
1. Go to [Kaggle Notebooks](https://www.kaggle.com/code)
2. Click "New Notebook" → Upload `palette-img2img-implementation.ipynb`

### Step 2: Configure Settings
- **Accelerator**: GPU T4 x2
- **Internet**: ON (for downloading checkpoints)
- **Persistence**: Session-only (or Save Version)

### Step 3: Add Dataset
1. Click "Add Data" (right panel)
2. Search: "CelebA-HQ resized 256"
3. Add: [badasstechie/celebahq-resized-256x256](https://www.kaggle.com/datasets/badasstechie/celebahq-resized-256x256)

### Step 4: Run!
```
Run All Cells (Ctrl+Enter)
```

**Expected Runtime**: ~15-20 minutes (including model download)

---

## 💻 Local Setup (Advanced)

### Prerequisites
```bash
# Python 3.8+, CUDA 11.0+ (for GPU)
python --version
nvidia-smi
```

### Installation
```bash
# 1. Clone repository
git clone https://github.com/YOUR_USERNAME/palette-face-inpainting.git
cd palette-face-inpainting

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Clone Palette repo
git clone https://github.com/Janspiry/Palette-Image-to-Image-Diffusion-Models

# 5. Download dataset
# Download from: https://www.kaggle.com/datasets/badasstechie/celebahq-resized-256x256
# Extract to: ./CelebA-HQ resized (256x256)/celeba_hq_256/

# 6. Download checkpoint
# Download from: https://drive.google.com/drive/folders/13YZ2UAmGJ-b7DICr-FDAPM7gctreJEoH
# Extract to: ./ckpt_celebahq/200/
```

### Update Paths in Notebook
Change these paths in the notebook cells:
```python
# From:
"/kaggle/input/"
"/kaggle/working/"

# To:
"./CelebA-HQ resized (256x256)/"
"./outputs/"
```

### Run
```bash
jupyter notebook palette-img2img-implementation.ipynb
```

---

## 📋 Execution Checklist

### Phase 1: Setup (Cells 1-3)
- [ ] Environment initialized
- [ ] Palette repo cloned
- [ ] Dependencies installed

### Phase 2: Data Preparation (Cells 4-7)
- [ ] Dataset found and loaded
- [ ] 20 test images prepared
- [ ] Checkpoint downloaded/found
- [ ] Config files generated

### Phase 3: Inference (Cells 8-11)
- [ ] Model loaded
- [ ] Inpainting completed
- [ ] Triptychs generated
- [ ] Results saved

### Phase 4: Verification (Cell 12)
- [ ] PSNR verification passed
- [ ] Triptychs look realistic

### Phase 5: Metrics Evaluation (Cells 14-24) [Optional]
- [ ] Packages installed
- [ ] Metrics calculated
- [ ] Visualizations generated
- [ ] Reports created

---

## 🎯 Expected Outputs

### After Inference (Cell 11)
```
/kaggle/working/triptychs_final/
├── trip_00000.png
├── trip_00001.png
├── ...
└── trip_00019.png

celebaHQ20_inpainting_triptychs_PRESENTABLE.zip
```

### After Evaluation (Cell 24)
```
outputs/
├── inpainting_metrics_detailed.csv
├── inpainting_metrics_summary.csv
├── comprehensive_metrics_visualization.png
├── metrics_correlation_heatmap.png
├── metrics_summary_table.csv
├── metrics_summary_table.tex
└── METRICS_REPORT.txt
```

---

## ❓ Troubleshooting

### "Dataset not found"
- **Kaggle**: Make sure CelebA-HQ is added via "Add Data"
- **Local**: Verify dataset path and folder structure

### "Checkpoint not found"
- **Kaggle**: Enable Internet to auto-download
- **Local**: Manually download from Google Drive link

### "CUDA out of memory"
- Reduce batch size (if modified)
- Use smaller image count (change from 20 to 10)
- Restart kernel and run again

### "Import errors"
- Re-run cell 15 to install packages
- Restart kernel after installation
- Check Python version (3.8+ required)

---

## 📊 Quick Results Check

After running inference, check:

1. **Visual Quality**
   - Open any `trip_*.png` file
   - Middle panel should look realistic
   - Should blend well with context

2. **Metrics (Cell 12)**
   ```
   Masked PSNR (Pred vs GT): ~25-30 dB ✓
   Masked PSNR (Noisy vs GT): ~5-10 dB ✓
   ```

3. **Verdict**
   ```
   VERDICT: ✅ These look like real, decent predictions.
   ```

---

## 🎓 Next Steps

1. **Customize Masking**
   - Edit cell 9: Adjust `mask_config` parameters
   - Experiment with different mask patterns

2. **Use Your Own Images**
   - Replace dataset in cell 5
   - Ensure 256×256 resolution

3. **Extend Evaluation**
   - Add custom metrics in cell 18
   - Create new visualizations

4. **Fine-tune Model**
   - See Palette repo for training scripts
   - Use your own dataset

---

## 💡 Tips

- **Kaggle GPU Hours**: Turn off GPU when not running cells
- **Save Work**: Click "Save Version" regularly
- **Download Results**: Click "Output" → Download all files
- **Share Results**: Make notebook public and share link

---

## 📞 Need Help?

- 📖 Read the full [README.md](README.md)
- 🐛 Report issues on [GitHub](https://github.com/YOUR_USERNAME/palette-face-inpainting/issues)
- 💬 Ask questions in GitHub Discussions

---

Happy inpainting! 🎨✨
