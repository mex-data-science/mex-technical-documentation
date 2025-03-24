# Project Structure: Perfect Order Masivo

The project is contained in the following path:  

**Workspace > Users > renata.ramos@loreal.com > Perfect Order Masivo**  

Within this directory, you'll find four notebooks:

## 1. `beauty_attributes_lemmatization`
- Extracts beauty attributes from:
  - The centroids of the beauty attributes segments.
  - The product descriptions.
- Compares and assigns the corresponding attributes to each product.
- Output is stored in:  
  **`crm_analytics.mex_fact_brand_tags`**.

## 2. `main_perfect_order_masivo`  
## 3. `main_perfect_order_masivo_2.0`
- These are the main notebooks of the project.
- The difference between them:
  - **Version 2.0** assigns different weights to attributes based on their importance in the segment.
  - **Version 1.0** gives equal weight to all attributes.
- Steps performed in these notebooks:
  1. Create the **segment matrix** and **product matrix**.
  2. Multiply these matrices to obtain the **segment-product matrix**.
  3. Generate a score for each segment-product pair.
  4. Store the ordered results in:  
     **`crm_analytics.mex_fact_perfect_order_masivo_2`**  
     **Alternative output** (all scores):  
     **`crm_analytics.mex_fact_perfect_order_masivo_segment_scores`**.

## 4. `Perfect Order Presentation Info`
- Contains visuals used for a presentation.
