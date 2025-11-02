### Part 1: Traditional Tidy Text Approach (Jane Austen)
- Uses tidytext package with lexicon-based methods (AFINN, Bing, NRC)
- Word-by-word sentiment scoring
- Effective for literary text analysis

### Part 2: Advanced Sentiment Analysis (Pride and Prejudice)
- Employs multi-dimensional emotion analysis using NRC lexicon to track eight distinct emotions (joy, anger, fear, trust, anticipation, surprise, sadness, disgust) across the   
  narrative arc
- Implements context-aware sentiment scoring with sentimentr package, which accounts for valence shifters like negations ("not happy") and amplifiers ("very good") for more nuanced 
  analysis
- Includes character-specific sentiment tracking to analyze how emotional tone shifts when major characters (Elizabeth, Darcy, Wickham) are mentioned, revealing character 
  development patterns
- Compares three distinct lexicons (AFINN, Bing, NRC) at both chapter and sentence levels to demonstrate methodological rigor and validate findings across different sentiment 

