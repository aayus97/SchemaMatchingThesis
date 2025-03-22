# SchemaMatchingThesis
This is my work while working on my masters thesis in the topic of Schema Matching


# Schema Matching with ML - TPC-DI Evaluation

## 1. Load and Clean JSON Schemas
- Parse source, target, and mapping
- Preview columns

## 2. Create Pairwise Feature Dataset
- Generate (src, tgt) pairs
- Compute similarity features
- Add labels

## 3. Train LightGBM Classifier
- Show feature importance
- Show performance

## 4. Predict and Rank Matches
- Show top 5 candidates for each source
- Visualize confidence

## 5. Evaluate Accuracy
- Top-1 Accuracy
- Top-3 Coverage
- Confusion matrix

## 6. Analyze Errors
- False positives
- Most common mismatches

## 7. Repeat for All Datasets
- Loop across folders
- Save results

## 8. Visualize Overall Results
- Barplots of accuracy
- Downloadable CSVs

flowchart TD
    A[Start] --> B[Load TPC-DI Dataset Folder]
    B --> C[Clean & Parse JSON Files]
    C --> D[Extract Source & Target Column Names]
    D --> E[Generate All (source, target) Pairs]
    E --> F[Compute Similarity Features]
    F --> G[Label Each Pair (match / no match)]
    G --> H[Train LightGBM Classifier]
    H --> I[Rank Target Matches For Each Source]
    I --> J[Evaluate: Top-1 Accuracy / Top-3 Coverage]
    J --> K{Is it last folder?}
    K -- No --> B
    K -- Yes --> L[Save Results to CSV]
    L --> M[Log False Positives]
    M --> N[Optional: Visualize & Debug]
    N --> O[Done]

