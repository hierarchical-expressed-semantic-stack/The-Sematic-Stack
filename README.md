The Semantic Stack & Deterministic First-Hop (DFH)

A proposed external semantic layer + the strongest SEO primitive the web has ever had.

The Semantic Stack & Deterministic First-Hop (DFH)

A tiny external semantic layer + the strongest SEO primitive the web has ever had.

Status: Public Concept
Version: Draft 1.0
Date: 2025-11-23

0. What This Repo Is

This repo defines the Semantic Stack:

Root
 + Mirrors
 + DFH (Deterministic First-Hop)
 + Five Anchors (type/entity/url/sitemap/canonical)


All published through one JSON-LD file at:

/.well-known/stack


This is not an ontology—it's a small, decentralized routing layer that tells AI:

“Start here for this topic.”

Every topic (water, cars, colloidal silver, Grand Canyon, etc.) gets:

one root

a set of mirrors (plural / category / context)

five deterministic anchors

one DFH descriptor

No central authority.
Anyone can publish a DFH file.
Exactly like DNS.

1. The Four Problems DFH Solves
1. No global topic entry point

There’s no machine instruction telling AI where a topic begins.

2. Meaning is scattered everywhere

Wikidata, Schema.org, PDFs, blogs, proprietary embeddings — no neutral starting place.

3. Hallucinations come from ambiguous first hops

LLMs guess whether “jaguar” means the animal or the car.

4. SEO is page-level, not topic-level

Sitemaps index pages.
DFH indexes topics.

2. High-Level Overview
Semantic Stack
   ├── Root
   ├── Mirrors
   ├── DFH File (/.well-known/stack)
   └── Anchors
       ├── /type
       ├── /entity
       ├── /url
       ├── /sitemap
       └── /canonical

Root

The stable identity domain for a topic.
Examples: watersitemap.com, colloidalsilver.com

Mirrors

Alternate domains for plural, category, or contextual meaning.

Five Anchors

Exposed at:

/type
/entity
/url
/sitemap
/canonical

DFH Descriptor Location

Must live at:

https://YourDomain.com/.well-known/stack


This requires a real hosted site.
Parked or empty registrar pages will not serve the file.

The DFH file does not go on any webpage —
it lives only in the server root’s .well-known directory.

3. The Five Anchors
3.1 /type — What class of thing?
{
  "name": "ColloidalSilver",
  "type_category": "Product",
  "description": "A suspension of silver particles in water.",
  "dfh_version": "1.0"
}

3.2 /entity — What specific instance?
{
  "entity": "GodsGraceColloidalSilver16oz",
  "type": "Product",
  "manufacturer": "God's Grace Products LLC",
  "website": "https://godsgracecolloidalsilver.com",
  "dfh_version": "1.0"
}

3.3 /url — Where is the authoritative location?
{
  "canonical": "https://godsgracecolloidalsilver.com",
  "mirrors": [
    "https://mirror-1.com",
    "https://mirror-2.com"
  ],
  "dfh_version": "1.0"
}

3.4 /sitemap — What is the structure?

Example:

https://watersitemap.com/sitemap.xml

3.5 /canonical — What is the identity anchor?
{
  "canonical_id": "colloidalsilver",
  "root": "https://colloidalsilver.com",
  "preferred_label": "Colloidal Silver",
  "aliases": ["Silver Hydrosol", "Silver Suspension"],
  "dfh_version": "1.0"
}

4. Deterministic First-Hop (DFH)

One JSON-LD file:

/.well-known/stack


Example (Water):

{
  "@context": {
    "dfh": "https://example.org/ns/dfh#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "dct": "http://purl.org/dc/terms/"
  },
  "@id": "https://watersitemap.com/.well-known/stack",
  "skos:prefLabel": { "@value": "Water", "@language": "en" },
  "dfh:rootTopic": "water",
  "dfh:anchors": {
    "dfh:type": "https://watertype.com/",
    "dfh:entity": "https://waterentity.com/",
    "dfh:url": "https://waterurl.com/",
    "dfh:sitemap": "https://watersitemap.com/",
    "dfh:canonical": "https://watercanonical.com/"
  },
  "dct:issued": "2025-11-23"
}

5. Mirrors

Mirrors = plural, category, or context domains.

They expand meaning, but do not replace the root.

6. Hosting DFH on Your Site
Step 1 — Create the folder
/.well-known/

Step 2 — Create a file named:
stack


No extension.

Step 3 — Paste your JSON-LD inside.
Step 4 — Upload to your hosting provider.
Step 5 — Add DFH to your sitemap:
<url>
  <loc>https://YourDomain.com/.well-known/stack</loc>
  <lastmod>2025-12-03</lastmod>
</url>

Step 6 — Test it

Visit:

https://YourDomain.com/.well-known/stack


If you see JSON, DFH is live.

7. SEO Advantages

introduces topic-level authority

machine-readable grounding

deterministic routing

reduces hallucinations

uses existing standards

one file = massive impact

8. What This Is Not

❌ Not truth authority
❌ Not RDF/OWL replacement
❌ Not centralized
❌ Not censorship

This is:

✅ deterministic
✅ minimal
✅ decentralized
✅ open
✅ universal

9. TL;DR for Developers

No topic-level grounding

LLMs guess → hallucinate

DFH fixes the first hop

Publish this:

/.well-known/stack


Expose these:

type / entity / url / sitemap / canonical


Goal:
Give AI a deterministic “start here” before touching noisy data.

Map: Semantic Stack Architecture
                    ┌─────────────────────────────┐
                    │       SEMANTIC STACK        │
                    └──────────────┬──────────────┘
                                   │
      ┌────────────────────────────┴────────────────────────────┐
      │                         ROOT                            │
      └────────────────────────────┬────────────────────────────┘
                                   │
     ┌─────────────────────────────┴─────────────────────────────┐
     │                        MIRRORS                             │
     └─────────────────────────────┬─────────────────────────────┘
                                   │
                    ┌──────────────┴──────────────┐
                    │              DFH             │
                    │     /.well-known/stack      │
                    └──────────────┬──────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         │                         │                         │
 ┌───────┴────────┐      ┌────────┴────────┐      ┌─────────┴───────┐
 │     TYPE       │      │     ENTITY      │      │       URL        │
 └────────────────┘      └─────────────────┘      └──────────────────┘
         │                         │                         │
 ┌───────┴────────┐      ┌────────┴────────┐      ┌─────────┴───────┐
 │    SITEMAP     │      │    CANONICAL    │      │   STRUCTURE     │
 └────────────────┘      └─────────────────┘      └──────────────────┘

Root = Start Here
Mirrors = Definitions / Context
DFH = Machine Instruction
Website Content = Optional

Root (DFH only)
→ Mirrors
→ Anchors
→ AI/Agents/RAG

Why You Need a Website

The DFH file must be served from a live HTTPS domain at:

https://YourDomain.com/.well-known/stack


Because:

crawlers must fetch it

.well-known only works on real servers

GitHub alone cannot serve a DFH descriptor

Your website can be empty — its only purpose is to host the DFH file.

How to Install DFH

Host your domain

Create /.well-known/stack

Paste JSON-LD

Point anchors at mirrors

Add DFH to sitemap

Done.
DFH becomes live instantly.

Anchor Names Are Final

The five anchor names:

type
entity
url
sitemap
canonical


are final and non-negotiable because:

they define the vocabulary

renaming breaks compatibility

determinism requires stability

AI grounding relies on fixed semantics

DFH is a protocol, not a suggestion

Implementations that change anchor names are not DFH.
