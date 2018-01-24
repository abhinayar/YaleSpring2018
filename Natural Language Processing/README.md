Class 3

01/23/2018

NLP

—

Word Segmentation:

- **--** Tokenization has some pitfalls
- **--** New York - Los Angeles vs. M-SP
- **--** Different languages pose diff. Problems
  - **--** Japanese
  - **--** Arabic
  - **--** Etc.
- **--**** Polyglot**
  - **--** StonyBrook U
  - **--** Diff. language support
  - **--** Python
- **--** Sentence Boundary Recognition:
  - **--** Decision trees
  - **--** Features:
    - **--** Punctuation, formatting, fonts, spacing, cap, etc.
    - **--** Needs to catch Dr., etc.

Tasks in NLP:

- **●●** POS tagging
  - **○○** How many POS in english? It depends… more than 7 or 8, and can be anywhere from 10ish to &gt; 20
- **●●** Parse Trees
  - **○○** Standard algo is to take a &quot;context free grammar&quot; and then generate a parse tree
  - **○○** Parsing-&gt; constituent parsing, is transforming sentences into the parse tree form
  - **○○** COMMON PARSER:
    - **■■** Stanford parser (web demo)
  - **○○** Dependency parsing
    - **■■** Parsers that output NO non-terminals
    - **■■** Instead you have exactly as many nodes as there are in the sentences + root node
    - **■■** Want to find most IMPORTANT word in the sentence
    - **■■** Easier to do, easier to train and needs less data. More SEMANTIC rep of the sentence (Q&amp;A, Machine trans., better/easier)
- **●●** INFORMATION EXTRACTION
  - **○○** For example -&gt; quant trading, auto analyst
- **●●** Semantics
  - **○○** FOL
  - **○○** Inference
  - **○○** Semantic Analysis
  - **○○** Semantics is the logical rep of the meaning of sentences
    - **■■** You want to capture MEANING as opposed to just surface level of the words
- **●●** Inference, reading comprehension
  - **○○** Take large blocks of text and understand it
  - **○○** FB Research does a lot of work on this
    - **■■** Babi Corpus
- **●●** Word Sense disambiguation
  - **○○** The thieves took off with 100 gold bars
    - **■■** What is bars here?
  - **○○** Done using word embeddings which is vector rep of words
- **●●** Named Entity Recognition
  - **○○** Related to info extraction
  - **○○** You have a running text and you have to figure out which words are POS, peoples, locations, companies, etc.
  - **○○** Univ. Illinois has large set of tools
- **●●** Question Answering
  - **○○** Watson
- **●●** Sentiment Analysis
  - **○○** Extract sentiment from the sentences based on key phrases etc
  - **○○** Facet specific sentiment
    - **■■** Can have diff. Sentiment for diff. Parts inside a sentence
- **●●** Machine Translation
  - **○○** Last assignment in class
- **●●** Text Summarization
  - **○○** Many input documents, one out
  - **○○** Find the &quot;gist&quot;
- **●●** Text to Speech processing
  - **○○** Synthesizers for speech from Facebook + Google
  - **○○** Amazing things like:
    - **■■** Natural voice
    - **■■** Expressive voice

Techniques in NLP:

- **●●** Lecture 115.
- **●●** Linguistic Knowledge
  - **○○** Knowing the types of phrases and how to dissect a sentence
  - **○○**
