---
layout: archive
title: "Lab Resources"
permalink: /resources/
author_profile: true
---

{% include toc %}

## Overview

Our lab develops computational tools and curates resources to advance research at the intersection of cancer biology, aging, and computational methods. On this page, you'll find our lab-developed software, curated learning materials, and research guides.

## Lab-Developed Software & Tools

<div class="tool-grid">
  <div class="tool-card">
    <h3>ecPath</h3>
    <p>A deep learning approach that detects extrachromosomal DNA (ecDNA) in tumors from routine histopathology images, making previously expensive analyses accessible through standard clinical data.</p>
    <div class="tool-links">
      <a href="https://www.biorxiv.org/content/10.1101/2024.11.13.623494v1" class="btn btn--primary">Paper</a>
      <a href="https://github.com/Sinha-CompBio-Lab/ecPATH" class="btn btn--primary">GitHub</a>
    </div>
  </div>

  <div class="tool-card">
    <h3>PERCEPTION</h3>
    <p>A computational framework that predicts patient response and resistance to treatment using single-cell transcriptomics of tumor samples.</p>
    <div class="tool-links">
      <a href="https://www.nature.com/articles/s43018-024-00756-7" class="btn btn--primary">Paper</a>
      <a href="https://github.com/ruppinlab/PERCEPTION" class="btn btn--primary">GitHub</a>
    </div>
  </div>
</div>

## Cancer & Aging Research Resources

Our lab curates computational resources specifically designed for researchers working at the intersection of cancer and aging. These resources span multiple biological scales and computational approaches.

### Data Resources & Methods Collections

<div class="resource-grid">
  <div class="resource-card">
    <h3>Big Data Resources in Cancer & Aging Research</h3>
    <p>A comprehensive collection of datasets, tools, and resources spanning genomics, transcriptomics, proteomics, and imaging data repositories.</p>
    <a href="https://x.com/Sanjusinha7/status/1570729265519546368" class="resource-link">View Resources <i class="fas fa-arrow-right"></i></a>
  </div>

  <div class="resource-card">
    <h3>Computational Methods for Spatial Transcriptomics</h3>
    <p>Guides and tools to help researchers implement spatial transcriptomics techniques, which are revolutionizing our understanding of tissue biology in aging and cancer.</p>
    <a href="https://x.com/Sanjusinha7/status/1578434020643205120" class="resource-link">Learn More <i class="fas fa-arrow-right"></i></a>
  </div>

  <div class="resource-card">
    <h3>Computational Methods to Probe the Immune System</h3>
    <p>A collection of computational approaches specifically designed for analyzing immune system dynamics and their role in aging and cancer progression.</p>
    <a href="https://x.com/Sanjusinha7/status/1576306476041515008" class="resource-link">Explore Methods <i class="fas fa-arrow-right"></i></a>
  </div>
</div>

### Learning Resources & Research Directions

<div class="resource-grid">
  <div class="resource-card">
    <h3>Machine Learning for Biomedical Research</h3>
    <p>A practical guide to implementing machine learning approaches in biomedical studies, with a focus on applications in aging and cancer research.</p>
    <a href="https://x.com/Sanjusinha7/status/1589735781736001536" class="resource-link">View ML Resources <i class="fas fa-arrow-right"></i></a>
  </div>

  <div class="resource-card">
    <h3>Open Questions in Aging Research</h3>
    <p>Key unsolved questions at the intersection of aging and cancer that represent exciting opportunities for computational biologists.</p>
    <a href="https://x.com/Sanjusinha7/status/1575529608174108672" class="resource-link">Explore Open Questions <i class="fas fa-arrow-right"></i></a>
  </div>
</div>

## Collaborations & Support

Interested in collaborating or need assistance with any of these resources? [Contact us](/contact/) to discuss potential research partnerships or technical support.

<!-- CSS for styling resource cards and grids -->
<style>
.tool-grid, .resource-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.tool-card, .resource-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
  transition: transform 0.2s, box-shadow 0.2s;
}

.tool-card:hover, .resource-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 15px rgba(0,0,0,0.1);
}

.tool-links {
  margin-top: 1rem;
  display: flex;
  gap: 1rem;
}

.resource-link {
  display: inline-block;
  margin-top: 1rem;
  font-weight: 600;
  text-decoration: none;
  color: #0066cc;
}

.resource-link:hover {
  text-decoration: underline;
}

@media (max-width: 768px) {
  .tool-grid, .resource-grid {
    grid-template-columns: 1fr;
  }
}
</style>
