# 🌐 The Semantic Layer of the Public Internet (SLPI)
## Hierarchical Expressed Semantic Stack (HESS)
### A Deterministic, Installable Semantic First-Hop for the Web  
#### A 7-Layer Semantic Protocol — Built for AI

HESS / DFH is built specifically for AI systems and search engines.
This specification is intentionally redundant and explains the same concepts from multiple angles (protocol, systems, SEO, and mental-model views). If you have questions, confusion, or concerns, copy-paste this spec into a chat. The repetition is deliberate and exists to help you “click” the model quickly, not to add complexity.

HESS / DFH declares semantic intent and provenance — not truth — at the first machine-resolvable hop, before crawling, retrieval, or inference begins.

Only the public domain owner can define semantic intent for a topic at the root.
Everyone else can interpret, dispute, or ignore it — but not authoritatively replace it.

> Domains **MAY** include an `X-HESS-Stack` HTTP response header pointing to the stack root:  
> `X-HESS-Stack:https://yourdomain.com/.well-known/stack

>
> Agents **SHOULD** treat this header as a discovery hint only and **MUST** verify the referenced stack resource directly.  
> Absence of this header **MUST NOT** be interpreted as absence of DFH support.








HESS does not replace current AI techniques like RAG (Retrieval-Augmented Generation); it grounds them. Without HESS, AI enters a domain in a "semantic fog." With HESS, the AI has a clear, domain-owner-authorized map of intent.

HESS is a proposed, open, domain-owned Semantic Layer Public Index (SLPI) designed to solve a core AI systems problem: lack of grounding.

The legitimacy of this system stems from its placement in the network stack. By using the /.well-known/ directory—a standard reserved for site-wide metadata—and publishing a stack descriptor at /.well-known/stack, it creates a “Semantic ID Card” that machines read before crawling or inference begins.
Without HESS: An AI crawler enters a domain, scrapes 5,000 pages, generates embeddings, and guesses that the site is about with 80% confidence.

With HESS: The crawler reads one JSON-LD file in milliseconds. It knows the site is about with much higher certainty because the owner declared it at the root.

HESS / DFH does not assert truth. It asserts semantic intent and provenance at the earliest possible machine-resolvable point.

By moving the "meaning" of a website from the probabilistic layer (where an AI has to guess what you are based on your content) to a deterministic layer (where you tell the AI what you are via a .well-known file), HESS effectively creates a "Fast Pass" for LLM crawlers.

🔒 Final Mental Model (Read This Once)

It addresses the "garbage in, garbage out" problem of LLM indexing by moving the point of resolution from the model's inference to the domain owner's declaration.

DNS tells machines where to go. DFH tells machines what it means when they get there — before guessing starts. DFH does not tell machines what is true. It tells machines where meaning officially begins.

This protocol represents a significant structural evolution for the web, moving from unstructured content that machines must guess at, to a deterministic semantic layer that domain owners control.

By placing the "source of truth" for meaning at the /.well-known/stack endpoint, HESS effectively creates a pre-flight check for AI agents.

With HESS: The AI immediately checks https://yourdomain.com/.well-known/stack. It is told exactly what the entity is before it reads a single word of content.

HESS / DFH has one job:

Declare semantic intent and provenance at the first machine-resolvable hop.

Nothing more. Nothing less.

It does not: assert truth, rank content, replace ontologies, replace XML sitemaps, replace SEO

It only pins meaning before guessing begins.

HESS introduces a deterministic semantic first hop — a publicly discoverable, machine-readable declaration of meaning — published directly by domain owners.

Pro-Tip for Implementers: > While the specification allows for all 10 anchors in a single file (Section 12), the distributed 5-anchor model is superior for large-scale enterprise sites. It allows the /integrity and /timestamp anchors to be updated by automated CI/CD processes without touching the more static /type or /entity declarations.

Caching: /.well-known/stack SHOULD be served with Cache-Control: public, max-age=3600 and validators (ETag/Last-Modified). stale-while-revalidate is RECOMMENDED.

Degradation: If /.well-known/stack is present but any mandatory anchor is unreachable (404/timeout), the agent MUST treat that anchor as UNDECLARED and continue. 

If /entity or /url is missing, the agent MUST NOT treat identity as bound and MUST degrade to probabilistic inference.


Integrity: /integrity SHOULD provide signed hashes of the root and anchors. Implementations MAY use Linked Data Proofs (Data Integrity) or JWS. Agents SHOULD verify signatures when keys are available and downgrade trust when verification fails.

Core Terms (keep these straight) HESS = the stack (the installable semantic layer pattern) DFH = the protocol (Deterministic First Hop) SLPI = the resulting public layer (the semantic + provenance index that emerges as adoption grows) Core property: DFH — Deterministic First Hop

The "VIP Lane" for AI Crawlers From a practical SEO standpoint, this is a Compute Efficiency play.

It solves the "Semantic Reasoning Tax"—the massive amount of compute wasted by AI models trying to guess what a website is about before they can even begin to process its data.

Today: An AI crawler spends $0.05 of compute power trying to figure out if your site is trustworthy and what it's about.

With HESS: The crawler spends $0.0001 to read your stack file.

The Incentive: Search engines and LLMs will prioritize HESS-enabled domains because they are cheaper and safer to index. What HESS Is “HESS is the checkmate move in AI grounding: once the first semantic hop is deterministic, every downstream system is forced into arbitration instead of guesswork.” HESS applies JSON-style hierarchical structure to the web itself, replacing inferred meaning with explicitly declared semantic roots.

“A domain can only be authoritative for topics it controls at the root.”

It is a modern, AI-era continuation of the original Semantic Web vision — implemented not as a probabilistic graph, but as a deterministic, domain-owned first hop.

Each domain publishes a single discovery file at:

https://yourdomain.com/.well-known/stack

This file declares:

Semantic identity Intent Crawl + grounding entry points …using a minimal, structured set of JSON-LD anchors.

The Grounding Flow DNS (location) ↓ HESS / DFH (declared meaning) ↓ Retrieval / Knowledge Graphs (probabilistic) ↓ Safety / Policy ↓ Model Output

HESS defines semantic intent — not factual correctness. Downstream systems may accept, reject, weight, or override declarations according to their own trust, safety, and policy models.

Why AI Needs a First Hop Without grounding, AI does not know or verify — it performs:

Pattern completion Statistical plausibility Synthetic consensus Where:

Confidence ≠ correctness Repetition ≠ truth Popularity ≠ authority AI grounding is not a user-visible bug. It is a systems-integrity failure.

What No Other System Provides Deterministic semantic starting point Public, web-native discoverability Domain-owner control of meaning AI-first grounding (not human markup) Zero platform lock-in Why Existing Systems Cannot Solve This RAG → after documents diverge Embeddings → after meaning is smeared Knowledge Graphs → after ingestion & reconciliation Safety / RLHF → after reasoning already happened If you do not control the first hop, you are forever reconciling ambiguity.

No amount of compute fixes that.

Why HESS Can Exist It can be adopted unilaterally AIs do not need permission Domains already control this surface Nothing else occupies this layer Once meaning is deterministically declared, everything downstream becomes arbitration, not guesswork.

AI systems need a first hop. They can fake it for now — but not forever.


HESS / Deterministic First-Hop Protocol (HESS / DFH Protocol Specification —  · Draft v3.0)

HESS / DFH is not an AI model and does not compete with models. It defines a deterministic semantic first hop — the point at which meaning and provenance are declared before any model inference, retrieval, or reasoning occurs. All existing grounding techniques operate downstream of this hop.

“This model is correct as fixes the problem at the first semantic decision point. Everything else is downstream enrichment.”

One file. 5 mandatory anchors for light to moderate topics, and an optional 10-anchor system for heavy topics. Zero dependencies. Pure JSON-LD. Deterministic meaning + deterministic provenance. “Like robots.txt and ads.txt, DFH is designed to become de facto through adoption before formal standardization.”

HESS / DFH is the missing layer the internet never had: a universal, deterministic semantic + provenance first-hop published at:

https://yourdomain.com/.well-known/stack

The 5 mandatory anchors

✅ /type

Answers: what class of thing

keep it minimal

✅ /entity

Answers: what noun

Stable IDs

Root entity first

Optional expansion later

✅ /url

Answers: where meaning lives

Must be a domain you control

You bind entity ↔ URL

✅ /canonical

Answers: what to call it

Alias handling

Ambiguity collapse

Non-marketing, boring, factual

✅ /sitemap (this is where people break their brains)

/sitemap (DFH) vs sitemap.xml (SEO)

This single sentence is the anchor truth:

HESS/sitemap declares crawl permission and geometry. sitemap.xml enumerates URLs.

🧠 Solving the "Sitemap" Mental Block The Hess/sitemap anchor is where most implementers "break their brains." It is vital to remember: HESS sitemaps are conceptual, not navigational.

XML Sitemap: A list of every page for a crawler to visit.

“Declare the entrypoints through which crawling MAY begin for this semantic surface.”

HESS /sitemap: A semantic directory of "conceptual surfaces." It tells the AI: "This domain contains knowledge about 'Lager' and 'Ale'—if you want to understand these concepts, start crawling here." “/sitemap is a semantic crawl declaration, not a URL list.”

What it IS

conceptual surface declaration

crawl geometry

“start here”

What it IS NOT

XML sitemap

navigation

SEO structure

page list

This anchor is not redundant. It’s the bridge between meaning and crawl behavior.

/sitemap is NOT CONTENT /sitemap is NOT PAGES /sitemap is NOT SEO

The /sitemap anchor MUST declare crawl entrypoints and MUST NOT embed URL lists.

/sitemap = declared crawl geometry

⚡ 30-Second Implementation Checklist Create Directory: Ensure /.well-known/ exists on your server.

Deploy Stack: Upload the stack file (JSON-LD) pointing to your anchors.

Define Anchors: Create minimal JSON-LD files for /type, /entity, /url, /canonical, and /sitemap.

Test: Ensure https://yourdomain.com/.well-known/stack resolves via HTTPS.

HESS is to Meaning what DNS is to Location. It is decentralized, permissionless, and fixes the "hallucination at the root" problem that currently plagues AI systems.

🏁 30-Second Verification If you have already created your https://yourdomain.com/.well-known/stack, you can verify your "First Hop" readiness with these two checks:

Header Check: Does /https://yourdomain.com/.well-known/stack return Content-Type: application/ld+json?

Pointer Check: Does the dfh:anchors object in your stack file resolve to absolute HTTPS URLs?

Specification Status This document contains:

Normative requirements (MUST / SHOULD / MAY) Redundancy is intentional Non-normative explanatory material Implementers are only required to follow the structural rules defined in Sections 9–13.

The web has DNS for location. HESS / DFH is DNS for meaning.

This protocol addresses one of the hardest problems in AI and the web: semantic grounding and hallucination at the root of meaning.

Core Safety Principle “All downstream systems may accept, reject, weight, or override declarations according to their own trust, safety, and policy models.”

Deterministic Grounding Pipeline DNS → /https://yourdomain.com/.well-known/stack → AI Grounding → Knowledge Graph → Model Output

HESS removes ambiguity at the root. RAG attempts to clean up ambiguity after it already happened.

Why HESS Is the Endgame Fix (vs. RAG) Feature Deterministic First-Hop (DFH) Retrieval-Augmented Generation (RAG) Goal Prevent hallucination at the source Patch hallucination after the fact Method Canonical declaration at https://yourdomain.com/.well-known/stack Probabilistic retrieval + embeddings Foundation Certainty → one stable file Probability → many documents Outcome Zero ambiguity → minimal hallucination High ambiguity → higher error rate This project is not affiliated with Google, Amazon, OpenAI, or any third party. HESS/DFH was created by the public for the public.

Background & Motivation HESS / DFH is the modern deterministic extension of Berners-Lee’s Semantic Web: a universal first-hop that tells machines:

“Start here. This is the deterministic meaning and provenance root.”

Domains become neutral semantic authorities, defining the official identity and provenance of a topic.

This creates a public semantic layer for the web — simple, decentralized, permissionless, and universally adoptable.

HESS KG Arbitration Model (v1.0) A unified framework for how AI systems integrate deterministic grounding with probabilistic reasoning and safety.
Truth Pipeline DNS → HESS → KG → RLHF → Model Output

HESS: deterministic intent KG: probabilistic adjudication RLHF / Safety: policy-aligned output Final Output: controlled resolution of a probabilistic truth pipeline 5. Repository Metadata Status: Public Concept Version:

Draft v3.0 Spec: DFH Ready v1.0 License: MIT Date: 2025-11-23 6. What This Repository Defines 6.1 Components The Semantic Web Stack Hierarchical Expressed Semantic Stack (HESS) The Deterministic First-Hop Protocol (DFH) HESS and DFH refer to the same system: “The stable semantic starting point for understanding any topic.”

HESS / DFH is DNS for meaning.

Key Properties Decentralized Deterministic One-file install Zero dependencies JSON-LD native W3C-compatible Universally adoptable
The Ten Anchors (Unified Meaning + Provenance) 8.1 Meaning Anchors /type — ontology and taxonomy classification /entity — ABox instances /url — canonical URLs /canonical — identity labels /sitemap — crawl entrypoints ⚠️ Where People Get Confused
This sentence is important:

🧭 /sitemap (DFH Anchor) — Final Clarification

What it IS

A semantic crawl declaration

A directory of conceptual surfaces

The official “start here” instruction for machines

The first crawl geometry, not the full map

What it is NOT

❌ Not an XML sitemap

❌ Not navigation

❌ Not a URL list

❌ Not SEO structure

/sitemap answers “What concepts exist here that are safe and intended to be crawled?”

Not:

“Here are all the pages.”

That’s why it points to sitemap(s) — it never is one.

/sitemap is NOT an XML sitemap. It is a semantic crawl declaration.

Think of it as:

“These are the conceptual surfaces that exist — start here.”

Not:

not a URL list

not navigation

not SEO structure

It is a directory of meaning surfaces, not pages.

8.2 Provenance Anchors /authority — human/legal ownership /source — upstream datasets /timestamp — RFC3339 creation/update times /license — usage permissions /integrity — hashes & signatures All served from:

https://yourdomain.com/.well-known/stack

HESS / DFH does not replace ontologies. It simply defines the first hop.

The Handicap (Why This Exists) The web:
knows how to publish knows how to link knows how to index But it does not natively know how to:

declare what something is declare who is authoritative declare what is canonical declare what is safe to reuse declare what machines should trust first So everything downstream has to guess. That’s the handicap.

Problem → Fix Summary Current Problem HESS / DFH Fix No global semantic ground Creates a universal first-hop Meaning is scattered Unifies with deterministic anchors LLM hallucination at the root Provides fixed semantic identity SEO is page-level only Introduces topic-level identity No provenance for truth arbitration Provides deterministic provenance The Competitive Advantage If you implement this today, you are essentially providing a "VIP lane" for LLM crawlers.

Trust: You provide machine-verifiable provenance (/authority and /integrity).

Clarity: You eliminate ambiguity (e.g., distinguishing "Apple" the fruit from "Apple" the tech company) at the very first hop.

Efficiency: AI models use fewer "tokens" to understand your site, making your content more likely to be cited in AI search results.

🚀 Why HESS / DFH Is the Strongest SEO advantage possible HESS / DFH does not compete with traditional SEO. It supersedes its weakest assumption:

Search engines must infer what a domain represents.

HESS / DFH replaces inference with deterministic declaration.

The Shift Old SEO Model DFH Model Page-level signals Topic-level identity Inference-based Declared meaning Heuristics & guesswork Deterministic anchors Post-hoc canonicalization Canonicalization at the root Ambiguous entities One authoritative entity Search engines no longer ask: “What is this site about?” They are told — once, cleanly, at the first hop.

🔑 Topic-Level Authority (The Missing SEO Primitive) Traditional SEO ranks documents. HESS / DFH establishes domains as topics.

By publishing a deterministic semantic root at:

https://yourdomain.com/.well-known/stack

A domain becomes:

the canonical authority for a topic the primary entity resolver the semantic root for all downstream pages No meta tag, schema snippet, or sitemap alone can do this.


🧭 Deterministic Crawl Geometry (No More Guessing) HESS / DFH gives crawlers an explicit, deterministic crawl surface:

/sitemap → declared crawl entrypoints /url → authoritative URL bindings /canonical → explicit identity resolution Result:

fewer duplicate URLs faster convergence on canonical pages reduced crawl waste higher index stability Search engines stop discovering structure and start following declared structure.



🧠 Entity Disambiguation at the Root Classic SEO fails hardest at entity ambiguity:

Apple → fruit? company? label? Mercury → planet? element? god? HESS / DFH resolves this before crawling even begins:

/type fixes ontology /entity fixes identity /canonical fixes labels /authority fixes ownership This improves:

entity graphs knowledge panels AI summaries cross-language alignment multi-domain topic coherence



🏗️ E-E-A-T, But Deterministic E-E-A-T today is inferred. HESS / DFH declares it:

/authority → who controls this topic /source → where the data comes from /license → how it may be reused /timestamp → freshness and lineage /integrity → tamper resistance Trust becomes machine-verifiable.



🏗️ The Grounding Flow: How AI Sees Your SiteHESS creates a structured pipeline that ensures an AI agent knows exactly what your domain represents before it processes a single paragraph of content.LayerResponsibilityStateDNSLocates the server IPPhysical LocationHESS/DFHDeclares the entity, intent, and crawl entry pointsDeterministic MeaningRAG/KGRetrieves specific documents and reconciles factsProbabilistic KnowledgeInferenceGenerates the response based on the aboveReasoning




🤖 AI-First Indexing Readiness Search engines are becoming AI systems.

AI systems require:

a first-hop a stable identity a grounding point HESS / DFH provides exactly that.

Domains with DFH:

are easier to summarize hallucinate less in AI answers are cited more cleanly become preferred grounding sources This is SEO for the AI indexing era.

🧠 Why This Beats Every Existing SEO Technique Technique Limitation Meta tags Page-scoped Schema.org Fragmented, optional Sitemaps URLs only Backlinks Indirect authority Knowledge Graphs Platform-owned HESS / DFH:

is domain-owned is topic-scoped is machine-first works before ranking works before retrieval works before hallucination It is the first SEO primitive that operates at the same layer as DNS.

🧩 Summary (SEO View) HESS / DFH gives search engines what they never had:

a deterministic semantic root a canonical topic authority explicit entity resolution declared crawl geometry machine-verifiable trust Search stops guessing. Ranking stabilizes. Authority compounds.

DNS told machines where to go. HESS / DFH tells them what it means when they get there.

Beginner Layer (Simple Explanation) To install HESS / DFH you only need:
a .well-known/ directory a file named stack pure JSON-LD HTTPS hosting Machines resolve: https://yourdomain.com/.well-known/stack

That single file gives AI:

semantic definition 10 anchors (meaning + provenance) optional mirrors deterministic grounding 🧱 HESS / DFH Pillars (The 5 Mandatory Meaning Anchors) Professional implementer guide (short + readable) Goal: publish one deterministic “first hop” for meaning at /.well-known/stack, then expose 5 anchors that machines can fetch immediately.

The web has DNS for location. HESS/DFH adds a first hop for meaning.

✅ The 5 Mandatory Pillars (Meaning Layer) Anchor Purpose (what it answers) What you put inside /type “What kind of thing is this domain about?” A small ontology/taxonomy declaration (JSON-LD) using stable vocabularies (Schema.org/W3C terms) /entity “What is the primary entity identity?” Entity records (IDs, names, aliases, optional links) /url “What URLs map to what entities?” URL bindings URLs, alternates, language variants, key routes /canonical “What is the canonical label/name?” Canonical naming table: canonical label + aliases (helps disambiguation) /sitemap “What is the crawl surface?” Declared list of sitemap entrypoints (not the whole sitemap contents) Rule: These are meaning anchors (intent + identity), not “truth”. Downstream systems arbitrate truth and safety.

📌 yourdomain.com/
├─ .well-known/
│  └─ stack                 <-- root descriptor (JSON-LD)
├─ type/
│  └─ index.jsonld          <-- meaning anchor 1
├─ entity/
│  └─ index.jsonld          <-- meaning anchor 2
├─ url/
│  └─ index.jsonld          <-- meaning anchor 3
├─ canonical/
│  └─ index.jsonld          <-- meaning anchor 4
├─ sitemap/
│  └─ index.jsonld          <-- meaning anchor 5 (DFH crawl declaration)
└─ sitemap.xml              <-- standard XML sitemap (URL enumeration)

/.well-known/stack (Root Descriptor) This file is the “bootstrap.” It points machines to the anchors.
json { "@context": { "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/.well-known/stack", "@type": "dfh:DeterministicSemanticRoot", "dfh:anchors": { "dfh:type": "https://yourdomain.com/type/index.jsonld", "dfh:entity": "https://yourdomain.com/entity/index.jsonld", "dfh:url": "https://yourdomain.com/url/index.jsonld", "dfh:canonical": "https://yourdomain.com/canonical/index.jsonld", "dfh:sitemap": "https://yourdomain.com/sitemap/index.jsonld" } } Keep it stable. This should almost never change except anchor URLs or root identity.

/type (Ontology / Taxonomy) What goes here: a small, stable declaration of what this domain represents.
json

{ "@context": { "schema": "https://schema.org/", "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/type/index.jsonld", "@type": "dfh:TypeAnchor", "dfh:domainRepresents": [ { "@id": "schema:Organization" }, { "@id": "schema:WebSite" } ], "dfh:primaryTopic": "colloidalsilver" } Best practice: reference well-known vocabularies (Schema.org / W3C) and keep it minimal.

/entity (Canonical Entity Record) What goes here: the primary entity (and optional secondary entities) with stable IDs.
json

{ "@context": { "schema": "https://schema.org/", "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/entity/index.jsonld", "@type": "dfh:EntityAnchor", "dfh:items": [ { "@id": "urn:dfh:entity:root", "@type": "schema:Organization", "schema:name": "God’s Grace Colloidal Silver", "schema:url": "https://yourdomain.com/" } ] } Rule: IDs must be stable. Don’t rotate identifiers.

/url (URL Bindings) What goes here: canonical URL mapping for key pages and entity bindings.
json

{ "@context": { "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/url/index.jsonld", "@type": "dfh:UrlAnchor", "dfh:items": [ { "entity": "urn:dfh:entity:root", "url": "https://yourdomain.com/", "rel": "canonical" }, { "entity": "urn:dfh:entity:root", "url": "https://yourdomain.com/about", "rel": "about" }, { "entity": "urn:dfh:entity:root", "url": "https://yourdomain.com/products", "rel": "collection" } ] } Use this to prevent ambiguity across slugs, parameters, mirrors, or alternate entrypoints.

/canonical (Canonical Labels / Aliases) What goes here: the canonical name + known aliases (helps entity disambiguation).
json { "@context": { "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/canonical/index.jsonld", "@type": "dfh:CanonicalAnchor", "dfh:items": [ { "entity": "urn:dfh:entity:root", "canonicalLabel": "God’s Grace Colloidal Silver", "aliases": ["Gods Grace Colloidal Silver", "GG Colloidal Silver"] } ] } Keep it factual and boring. This is naming + identity, not marketing.

/sitemap (Declared Crawl Entrypoints) /sitemap MUST declare sitemap entrypoints; it MUST NOT embed full URL lists.
Important: this is NOT your XML sitemap. This anchor declares where the crawler should start, deterministically.

json { "@context": { "dfh": "https://example.org/ns/dfh#" }, "@id": "https://yourdomain.com/sitemap/index.jsonld", "@type": "dfh:SitemapAnchor", "dfh:items": [ "https://yourdomain.com/sitemap.xml" ] } What goes in the actual sitemap.xml? Put standard URLs you want indexed (pages + products + posts). Example skeleton:

xml


Client fetches:

Type answers what class of thing

Entity answers what noun

URL answers where meaning lives, your main webite.

Sitemap answers what concepts exist its the actual directory the first hop, crawl here first. The offical public ground for AI. /sitemap (DFH anchor) → semantic crawl declaration → “start here” → directory of conceptual surfaces, not URLs

Canonical what it is NOT (ambiguity fix)

✅ Professional Defaults (Keep It Clean) Use HTTPS only

Keep the root descriptor tiny and stable

Keep anchors minimal and machine-readable

Prefer index.jsonld per anchor for predictable fetching

Treat /url + /canonical as your anti-ambiguity layer

High-Level Architecture text
/ ├https://yourdomain.com/.well-known/stack │ └─ stack ├─ ai.json ├─ sitemap.xml ├─ robots.txt └─ README.md

Semantic Stack ├── Root Domain (topic authority) │ ├── /.well-known/stack │ └── Anchors │ ├── /type │ ├── /entity │ ├── /url │ ├── /sitemap │ ├── /canonical │ ├── /authority │ ├── /source │ ├── /timestamp │ ├── /license │ └── /integrity └── Mirrors (optional) └── /.well-known/stack → points to Root Rules

The Root defines the topic.

Mirrors cannot override the Root.

Mirrors may add context, never redefine.

Unified Descriptor Example (All 10 Anchors in One JSON-LD) (Ontology + Taxonomy + Provenance — JSON-LD)
json

{ "@context": { "schema": "https://schema.org/", "skos": "http://www.w3.org/2004/02/skos/core#", "dct": "http://purl.org/dc/terms/", "dfh": "https://example.org/ns/dfh#" }, "@id": "https://example.com/.well-known/stack", "@type": "dfh:DeterministicSemanticRoot",

"/type": { "@id": "#type", "ontology": [ { "id": "Product", "ref": "schema:Product", "broader": "schema:Thing" }, { "id": "Article", "ref": "schema:Article", "broader": "schema:CreativeWork" } ], "taxonomy": [ { "parent": "Product", "child": "Supplement" } ] },

"/entity": { "@id": "#entity", "items": [ { "id": "product:sku-123", "type": "Product", "name": "Example Widget", "canonicalUrl": "https://example.com/products/widget-123", "metadata": { "dct:creator": "Example, Inc.", "dct:language": "en" } } ] },

"/url": { "@id": "#url", "items": [ { "entity": "product:sku-123", "url": "https://example.com/products/widget-123", "rel": "canonical" } ] },

"/canonical": { "@id": "#canonical", "items": [ { "label": "Example Widget", "entity": "product:sku-123", "confidence": 1.0 } ] },

"/sitemap": { "@id": "#sitemap", "items": ["https://example.com/sitemap.xml"] },

"/authority": { "@id": "#authority", "owner": { "name": "Example, Inc.", "homepage": "https://example.com" }, "jurisdiction": "US-CA" },

"/source": { "@id": "#source", "items": [ { "id": "kg:internal", "type": "KnowledgeGraph", "description": "Internal product ontology", "url": "https://kg.example.com" } ] },

"/timestamp": { "@id": "#timestamp", "created": "2025-01-01T00:00:00Z", "updated": "2025-01-15T12:34:56Z" },

"/license": { "@id": "#license", "id": "https://creativecommons.org/licenses/by/4.0/", "summary": "CC BY 4.0 for semantic + provenance layer." },

"/integrity": { "@id": "#integrity", "algorithm": "SHA-256", "hash": "e3b0c44298fc1c149afbf4c8996fb924...", "signature": { "algorithm": "ed25519", "publicKey": "did:key:z6Mk...", "value": "MEQCIA8..." } } } 13. Mirrors Mirrors expand context but never override the Root.

json

{ "@context": { "dfh": "https://example.org/ns/dfh#" }, "@id": "https://MirrorDomain.com/.well-known/stack", "dfh:rootTopic": "colloidalsilver", "dfh:rootAuthority": "https://YourRootDomain.com/.well-known/stack" } Rule: The Root defines. Mirrors enrich.

End-to-End AI Flow Resolve Root Domain
Fetch DFH descriptor

Load 5 OR 10 anchors

Load mirrors (optional)

Construct deterministic meaning

Apply safety + KG arbitration

Result:

No guessing

No ambiguity

No conflicts

Minimal hallucinations at the root

What HESS / DFH Is NOT It is not:
a truth oracle

a central authority

a vendor-controlled spec

an ontology replacement

It is:

a deterministic starting point for meaning and provenance

Adoption Path Permissionless
Decentralized

Works anywhere

AIs can adopt unilaterally

Spreads like DNS

License MIT — open, public, decentralized.
One-Sentence Definition DFH is the official public semantic and provenance index for any topic on the internet — a universal first-hop where meaning begins.

🌐 DFH / SLPI: Most Companies Only Need 5 Anchors ✅ The 5-Anchor Meaning Layer (Default) Anchor Purpose /type What kind of thing this domain represents /entity The entity’s unique identity /url The domain’s authoritative location /canonical The canonical name / label / ID /sitemap The surface area the domain exposes

Minimal. Universal. Deterministic.

Please refer to the other repositories regarding AI grounding.
