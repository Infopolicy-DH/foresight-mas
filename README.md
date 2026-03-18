Overview
FORESIGHT MAS is a multi-agent AI pipeline developed by FactCheck.LT (VšĮ DigitalHub, Vilnius, Lithuania) for systematic analysis of information manipulation across the Belarus-Russia media ecosystem and its impact on EU countries.
The system monitors cross-platform content (YouTube, TikTok, Telegram, web publications) in Russian, Belarusian, and other languages, detecting coordinated inauthentic behavior, tracking narrative manipulation, and producing automated threat assessments.
Architecture
┌─────────────────────────────────────────────────────────┐
│                    DATA COLLECTION                       │
│  YouTube API · TikTok (Oxylabs 4β) · Telegram · Web     │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│              KNOWLEDGE BASE (1M+ documents)              │
│         PostgreSQL / pgvector · Semantic search           │
│         Embeddings · Metadata · Cross-references          │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│              12-AGENT ANALYSIS PIPELINE                   │
│                                                          │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │
│  │ Content  │ │ Toxicity │ │Sentiment │ │ Narrative│   │
│  │ Analyst  │ │ Detector │ │ Analyst  │ │ Tracker  │   │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │
│  │Coordina- │ │ Cross-   │ │Forecaster│ │ Progress │   │
│  │tion Det. │ │ Platform │ │          │ │ Tracker  │   │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │
│  │ Segment  │ │ Codebook │ │ Vision   │ │ Synthe-  │   │
│  │ Analyst  │ │ Classifier│ │ (Thumb.) │ │ sizer    │   │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                    OUTPUTS                                │
│  Monthly reports · Threat alerts · Data journalism        │
│  Synthetic surveys · MATRA 12-country monitoring          │
└─────────────────────────────────────────────────────────┘
Research Streams
1. Coordinated Inauthentic Behavior Detection
Cross-platform analysis detecting coordination patterns across YouTube, TikTok, and Telegram. Key results:

TikTok coordination networks identified with statistical significance P<10⁻⁸⁰ during Polish presidential elections (53,357 videos from 5,924 accounts analyzed)
Cross-border synchronization documented between Belarusian and Russian state media during Poland railway sabotage campaign (7-minute coordination window)
Electoral interference patterns tracked across 4 EU countries

2. Multimodal Content Analysis
Monthly pipeline processing 1,700+ YouTube videos with:

Transcript analysis using codebook classification (v3)
Vision LLM thumbnail analysis for visual propaganda detection
Cross-platform narrative tracking

3. Synthetic Survey Methodology
LLM-inferred attitudes methodology for estimating public opinion in information-restricted environments where traditional polling is impossible:

Sociodemographic persona-based LLM agents
Validated against Chatham House Wave XVII benchmarks
A/B faithfulness testing across multiple LLM providers

4. Semantic Capture Analysis
Quantitative measurement of how state propaganda appropriates civil society terminology:

Substitution Index — a novel metric measuring semantic displacement over time
Characteristic V-curve patterns identified in 1M+ document corpus
Applied to 4-year longitudinal study of Ukraine war coverage (488,635 publications)

5. AI and Digital Security for Civil Society
Research on safe AI deployment for organizations operating under hostile digital surveillance (supported by German Marshall Fund):

Threat modeling for activists using LLM-based tools
Safe AI adoption frameworks for sensitive data contexts
Train-the-trainer program: 44 CSO representatives trained as "AI Champions"

Data Sources
PlatformScaleMethodYouTube16,000+ transcripts, 1,700+ videos/monthYouTube API, transcript extractionTikTok53,000+ videos (elections study)Oxylabs Project 4β (pro bono)TelegramChannels monitoringAPI collectionWebNews sites, state mediaWeb scraping pipeline
Total corpus: 1,100,000+ documents in Russian, Belarusian, English, and other languages.

Selected Publications

Monthly Foresight Reports — How Belarusian state media talks about EU neighbours → factcheck.lt
TikTok & Polish Elections — Coordinated manipulation analysis with P<10⁻⁸⁰ statistical proof
The Year of the Belarusian Woman — Data journalism piece based on 1M+ document corpus (4 languages)
Ukraine War Coverage — 4-year analysis of 488,635 publications
FIMI Advent Calendar — 31 global disinformation cases (4 languages)
Belarusian Media Landscape — Chapter in "Беларусский ежегодник" (Belarusian Yearbook)

Technology Stack

Database: PostgreSQL with pgvector extension (semantic search)
LLM APIs: Anthropic Claude, OpenAI GPT (comparative analysis)
Automation: n8n workflow engine
Data collection: Oxylabs (pro bono partnership), YouTube API, custom scrapers
Analysis: Python, multi-agent orchestration
Visualization: Python (matplotlib, plotly), custom data journalism templates

About FactCheck.LT
FactCheck.LT (registered as VšĮ DigitalHub in Lithuania) is a nonprofit research organization based in Vilnius, specializing in AI-powered disinformation analysis and digital security for civil society. The organization operates as part of the Belarusian democratic media ecosystem in exile, providing analytical products for EU institutions, diplomatic missions, civil society organizations, and independent media.

License
This repository contains methodology descriptions and documentation. The analytical pipeline code is not publicly available due to the sensitive nature of the work and operational security requirements. For research collaboration inquiries, please contact us through infopolicy.net.

© 2026 FactCheck.LT (VšĮ DigitalHub). Methodology descriptions may be referenced with attribution.
