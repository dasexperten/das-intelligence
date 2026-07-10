# Link Prospecting & Outreach

## Purpose

Run the earned-link half of a domain-authority program end to end: discover relevant link targets,
verify them, find a real contact email, draft a persuasion-optimized pitch in the target's language,
and send it through the controlled email gate — at fan-out scale, multilingual.

## When to Use

Use this skill when the task is to:

- find editorial roundups, review blogs, directories, or trade sites that could link/cite the brand;
- build a qualified, deduped outreach pipeline (optionally across many language markets);
- write pitches that maximize the yes-rate;
- execute low-volume, personalized outreach through an approved sending pipeline.

## When Not to Use

Do not use for paid link placements or PBNs (forbidden), for pure on-page SEO, or for automatic
API/no-captcha submissions (use `auto-backlink-submitter` — always run that first, it's cheaper per
link).

## Inputs

Brand facts (verbatim product specs, differentiators, links per angle), target keywords/markets,
languages, an approved sender identity, and the list of domains already contacted (to dedupe).

## Core Principle

**Make saying yes effortless, and never fabricate.** The pitch leads with the reader's benefit and
hands over a ready-to-paste entry + a free sample offer + (where the site monetizes that way) an
affiliate offer — so inclusion costs the editor nothing. Every claim is a verbatim product fact; no
invented awards, numbers, or addresses.

## Workflow

1. **Prospect (fan-out).** One researcher per market/category/keyword-angle sweeps the web for live
   targets; return per candidate: name, URL, opportunity type, language, cost, link type, why-it-fits.
2. **Dedup + verify.** Drop domains already contacted; verify each is live, relevant, and obtainable
   (free/earned, not pay-only). Normalize URLs before host-dedup (protocol-less URLs break parsing).
3. **Find the contact email.** One agent per target hunts the real contact/editorial address
   (contact/about/imprint/masthead; decode obfuscated addresses; never guess). No email → route to
   the semi-manual / contact-form flow.
4. **Draft persuasively, in-language.** Per target: reference their specific page, lead with the
   best-fit product for their angle, offer sample + ready-to-paste entry + affiliate option, keep the
   dense authority terms verbatim, 100–150 words, native language, no fabricated signature.
5. **Send through the gate.** Route every send through the estate's email delivery skill with the
   virtual-staff signature and the pre-send confirmation gate. Low daily volume, one at a time.
6. **Log + learn.** Record each send (target, address, message id, status). Feed replies into the
   self-learning playbook — double down on angles that earn links.

## Multi-agent notes (repeatable harness)

- Prospect and email-find are independent per target → fan out in parallel.
- Use a **per-item** output schema, not a strict enum on a whole array — one off-spec field must not
  null an entire finder batch.
- Recover from a failed post-processing step by reading the run journal (candidates are preserved
  there) rather than re-running the finders.

## Output

A deduped, verified target table; a real contact email per reachable target; a send-ready native
pitch per target; and a sent-log with message ids and statuses. Unreachable targets handed off with
paste-ready copy.

## Common Mistakes

- Emailing before checking the site publishes an address (most expose only a contact form).
- Generic mass-mail tone — always reference the specific page.
- Sending outside the approved gate / signature system, or in bulk without personalization (spam
  flags).
- Fabricating emails, specs, or a fake affiliate program (offer to set one up; don't claim one).
