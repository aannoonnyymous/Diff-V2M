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
Video-to-music (V2M) generation aims to create music that aligns with visual content. Existing methods often focus on high-level semantics while overlooking fine-grained temporal structures, limiting the coherence between video and musical progression. To address this gap, we propose Diff-V2M, a general video-to-music generation framework based on a hierarchical conditional diffusion model. To better capture temporal dynamics, we begin by evaluating several rhythmic representations, including low-resolution mel-spectrograms, tempograms, and onset detection functions (ODF), and identify  the low-resolution ODF as an effective signal for modeling musical rhythm. Built upon these insights, we design Diff-V2M with two key components: a feature extraction module and a conditional music generation module. Specifically, emotional, semantic, and rhythmic features are extracted from video inputs and incorporated into the generator via a hierarchical cross-attention mechanism, providing rich and temporally aligned conditioning signals. Additionally, to enhance feature integration, we introduce a set of timestep-aware fusion strategies, including feature-wise linear modulation (FiLM) and weighted fusion, allowing the model to adaptively balance semantic and rhythmic cues throughout the diffusion process. Extensive experiments demonstrate that Diff-V2M outperforms existing models on both in-domain datasets and the out-of-domain V2M-Bench dataset, achieving superior performance in terms of objective metrics and subjective comparisons.
Demos are available at [here](https://aannoonnyymous.github.io/Diff-V2M/).

## Comparisons with SOTA
<h3 align="center" style="color: black; font-weight: bold;">BGM909 Test Dataset </h3>

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
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/212_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    
    <tr>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/103_13-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/88_3-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/184_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/BGM-demo/600_11-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

<h3 align="center" style="color: black; font-weight: bold;">SymMV Test Dataset</h3>

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
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/179_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    
    <tr>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/212_5-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/153_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/227_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/SymMV-demo/959_9-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

<h3 align="center" style="color: black; font-weight: bold;">V2M-Bench Test Dataset</h3>

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
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/1-q8C_c-nlM_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
    
    <tr>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/3Gz8hP1QEO0_7-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/xv4LGfH5MWw_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZTttCukWDgw_1-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>

    <tr>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-VidMuse.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-GVMGen.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-MuMu.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-v2m.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
      <td><video width="230" controls preload="none"><source src="video/V2M-Bench-demo/ZrZ3rUgdkzU_0-CMT.mp4" type="video/mp4">Your browser does not support the video tag.</video></td>
    </tr>
  </tbody>
</table>

## More Samples Generated by Diff-V2M
<table>
  <tr>
    <td>
      <video width="345" controls preload="none">
        <source src="video/BGM-demo/3_6.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/SymMV-demo/287_0.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/BGM-demo/8_4.mp4" type="video/mp4">
      </video>
    </td>
  </tr>
  
  <tr>
    <td>
      <video width="345" controls preload="none">
        <source src="video/SymMV-demo/21_6.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/SymMV-demo/1056_0.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/SymMV-demo/85_9.mp4" type="video/mp4">
      </video>
    </td>
  </tr>

  <tr>
    <td>
      <video width="345" controls preload="none">
        <source src="video/V2M-Bench-demo/ZnViLnjcWzM_3.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/V2M-Bench-demo/ZV8zA3dFEO4_3.mp4" type="video/mp4">
      </video>
    </td>
    <td>
      <video width="345" controls preload="none">
        <source src="video/BGM-demo/14_10.mp4" type="video/mp4">
      </video>
    </td>
  </tr>
</table>
