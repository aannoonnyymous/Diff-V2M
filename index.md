---
layout: default
title: "Diff-V2M: A Hierarchical Conditional Diffusion Model with Generalizable Rhythmic Modeling for Video-to-Music Generation"
---
<style>
/* 修改页面主标题字体大小 */
.project-name {
  font-size: 36px !important;
  max-width: 1200px;
  margin: auto;
  text-align: center;
  word-break: break-word;
}
.main-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
</style>


## Abstract
Video-to-music (V2M) generation aims to create music that aligns with visual content. However, two main challenges persist in existing methods: (1) the lack of explicit rhythm modeling hinders audiovisual temporal alignments; (2) effectively integrating various visual features to condition music generation remains non-trivial. To address these issues, we propose Diff-V2M, a general V2M framework based on a hierarchical conditional diffusion model, comprising two core components: visual feature extraction and conditional music generation. For rhythm modeling, we begin by evaluating several rhythmic representations, including low-resolution mel-spectrograms, tempograms, and onset detection functions (ODF), and devise a rhythmic predictor to infer them directly from videos. To ensure contextual and affective coherence, we also extract semantic and emotional features. All features are incorporated into the generator via a hierarchical cross-attention mechanism, where emotional features shape the affective tone via the first layer, while semantic and rhythmic features are fused in the second cross attention layer. To enhance feature integration, we introduce timestep-aware fusion strategies, including feature-wise linear modulation (FiLM) and weighted fusion, allowing the model to adaptively balance semantic and rhythmic cues throughout the diffusion process. Extensive experiments identify low-resolution ODF as a more effective signal for modeling musical rhythm and demonstrate that Diff-V2M outperforms existing models on both in-domain datasets and out-of-domain dataset, achieving state-of-the-art performance in terms of objective metrics and subjective comparisons.
Demos are available at [here](https://aannoonnyymous.github.io/Diff-V2M/).

## Comparisons with SOTA
<h3 align="center" style="color: black; font-weight: bold;">BGM909 Test Dataset </h3>
<details>
  <summary><strong>Click to show videos</strong></summary>

  <br>
  <table>
    <thead>
      <tr>
        <th>Diff-V2M (ours)</th>
        <th>VidMuse</th>
        <th>GVMGen</th>
        <th>MuMu-LLaMA</th>
        <th>Video2Music</th>
        <th>CMT</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/212_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
      
      <tr>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/103_13-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/88_3-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/184_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls loading="lazy"><source src="video/BGM-demo/600_11-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
    </tbody>
  </table>
</details>
<h3 align="center" style="color: black; font-weight: bold;">SymMV Test Dataset</h3>
<details>
  <summary><strong>Click to show videos</strong></summary>

  <br>
  <table>
    <thead>
      <tr>
        <th>Diff-V2M (ours)</th>
        <th>VidMuse</th>
        <th>GVMGen</th>
        <th>MuMu-LLaMA</th>
        <th>Video2Music</th>
        <th>CMT</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/179_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
      
      <tr>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/212_5-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/153_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/227_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/SymMV-demo/959_9-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
    </tbody>
  </table>
</details>
<h3 align="center" style="color: black; font-weight: bold;">V2M-Bench Test Dataset</h3>
<details>
  <summary><strong>Click to show videos</strong></summary>

  <br>
  <table>
    <thead>
      <tr>
        <th>Diff-V2M (ours)</th>
        <th>VidMuse</th>
        <th>GVMGen</th>
        <th>MuMu-LLaMA</th>
        <th>Video2Music</th>
        <th>CMT</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
      
      <tr>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
  
      <tr>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
        <td><video width="230" controls><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      </tr>
    </tbody>
  </table>
</details>
## More Samples Generated by Diff-V2M
<details>
  <summary><strong>Click to show videos</strong></summary>

  <br>
  <table>
    <tr>
      <td>
        <video width="345" controls>
          <source src="video/BGM-demo/3_6.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/SymMV-demo/287_0.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/BGM-demo/8_4.mp4" type="video/mp4">
        </video>
      </td>
    </tr>
    
    <tr>
      <td>
        <video width="345" controls>
          <source src="video/SymMV-demo/21_6.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/SymMV-demo/1056_0.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/SymMV-demo/85_9.mp4" type="video/mp4">
        </video>
      </td>
    </tr>
  
    <tr>
      <td>
        <video width="345" controls>
          <source src="video/V2M-Bench-demo/ZnViLnjcWzM_3.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/V2M-Bench-demo/ZV8zA3dFEO4_3.mp4" type="video/mp4">
        </video>
      </td>
      <td>
        <video width="345" controls>
          <source src="video/BGM-demo/14_10.mp4" type="video/mp4">
        </video>
      </td>
    </tr>
  </table>
</details>
