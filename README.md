# BERT Tokenizer Analysis 

Exploring how BERT tokenizes different types of text —
from English to Nepali, math equations to Python code.

## What this project does
Tests and analyzes how BERT's tokenizer handles different
types of text to understand its strengths and limitations.

## What I discovered

### What BERT handles perfectly
- Common English words → single tokens
- Python code → every keyword recognized
- Math equations → handles algebra and Greek letters
- Western names → John, Emma = single tokens

### What BERT struggles with
- Nepali words → broken into meaningless pieces
- South Asian names → Sambridhi = 3 pieces, Priya = 2 pieces
- Nepali currency → "rupees" and "paisa" split up
- Nepal flag emoji 🇳🇵 → [UNK] completely unknown

## Key concepts learned

**Subword tokenization**
Unknown words get broken into smaller familiar pieces:
"Sambridhi" → ['sam', '##bri', '##dhi']
"momo"      → ['m', '##omo']

**Special tokens**
[CLS] (101) → marks start of every sentence
[SEP] (102) → marks end of every sentence
[UNK] (100) → unknown token BERT can't recognize

**Cased vs Uncased**
uncased → converts everything lowercase, recognizes more whole words
cased   → preserves capitals, better for names and places

**Token IDs are universal**
Every person using bert-base-uncased gets identical token IDs.
"i" is always 1045 regardless of who runs the code.

## The gap I found
BERT has almost no Nepali language support:
- Nepali words get broken into characters
- Nepali names split into meaningless pieces  
- Nepali currency words unrecognized
- Devanagari script barely supported

This reveals a real opportunity — a proper Nepali NLP
model with Nepali vocabulary and tokenizer is needed.

## Experiments run
- English sentences and common words
- Nepali words (मोमो, माया)
- Mathematical equations (y = mx + c, E = mc²)
- Greek symbols (α β γ δ)
- Python code (for loops, print statements)
- South Asian vs Western names comparison
- Nepali vs English currency words
- Emoji tokenization 🇳🇵
- Cased vs uncased comparison

## Built with
- Python
- Hugging Face Transformers
- Google Colab

## Background
Day 12 of my ML learning journey.
I am a software engineering student from Nepal
learning ML from scratch — starting from vectors and
dot products all the way to analyzing real pretrained models.

The Nepali language gap I discovered here is something
I plan to address in a future project — a proper
Nepali NLP model built by a Nepali student.
