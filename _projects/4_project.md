---
layout: page
title: Network Analysis
description: Project done for CSO323 (Graph Theory and its Applications) course
img: assets/img/na1.png
importance: 4
category: work
related_publications: false
---

This project focuses on the analysis of a protein-protein interaction (PPI) network in yeast, where proteins are represented as nodes and their interactions as edges. The objective was to study the network's topology and structure, identify communities, and analyze properties such as degree distribution, clustering, closeness, and eccentricity to understand the organization of the protein interaction network.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/na2.png" title="data" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Data Overview
</div>

The PPI network was modeled as an undirected and unweighted graph and analyzed using network analysis techniques and Gephi. We examined fundamental network properties including degree distribution, connected components, average path length, diameter, density, and clustering coefficient. Community detection was performed to identify densely connected groups of proteins, while closeness and eccentricity were analyzed to study node reachability and positions within the network. The network contained 2,018 nodes and 2,930 edges, with an average degree of 2.903 and a graph density of 0.001, indicating a sparse network. The average path length was 5.61, while the network diameter was 14. The degree distribution was highly skewed, with a minimum degree of 0 and a maximum degree of 92, indicating the presence of hub proteins. The network exhibited a moderate average clustering coefficient of 0.134. Community analysis identified 208 communities with a modularity of 0.753, suggesting a well-defined community structure. The network also contained 185 connected components. Analysis of the degree distribution and its long tail indicated that the network follows a scale-free structure, characterized by many low-degree nodes and relatively few highly connected nodes. Closeness and eccentricity distributions further indicated that many nodes are relatively distant from one another, while only a small number occupy more central positions in the network.

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/na6.png" title="result analysis" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/na3.png" title="result analysis" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/na4.png" title="result analysis" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/na5.png" title="result analysis" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="caption">
        Results from our Analysis
</div>

The analysis revealed that the yeast protein-protein interaction network is a sparse, scale-free network with a strong community structure. The presence of highly connected hub proteins alongside many low-degree proteins highlights the heterogeneous organization of the network. Community, clustering, closeness, and eccentricity analyses provided complementary insights into how proteins are organized and connected within the overall interaction network. 

To learn more about this project, please refer to the full project  <a href="https://drive.google.com/file/d/1YgkD6gBoa66ZJbA00T24tfISgX_MiffK/view?usp=sharing" target="_blank">slides</a>.
