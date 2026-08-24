BODY TRANSFORMATION TRACKER (BTT) 2.0.0 RC1
=============================================

BTT is an AI Dungeon scripting library that maintains canonical Player/NPC identity,
anatomy, appearance, temporary transformation state, Conditions, and Developable
Risks. It uses a shared evidence/confidence model so owner, source, receiver, slot,
and causal mechanism are resolved before state changes are committed.

RELEASE STATUS
--------------
This package is Release Candidate 1 for BTT 2.0. The runtime is feature-complete for
the planned 2.0 release. Scenario-specific card revisions will be reviewed separately
before the companion scenario packages are published.

INSTALLATION
------------
1. Add the complete BTT2.0_RC1.txt file to the scenario as a Library script.
2. In the AI Dungeon Input script, call:
      BTT("input");
3. In the Context script, call:
      BTT("context");
4. In the Output script, call:
      BTT("output");
5. Include the Gender and Heritage profile cards needed by the scenario. The included
   BTT2.0_Standard_Profile_Cards.json contains the nine standard Gender profiles and
   the standard Human Heritage profile used by the current BTT distribution.
6. Start or reload the scenario. BTT creates/maintains Configure BTT and BTT NPC
   Targets control cards and materializes four canonical cards for tracked entities.

IMPORTANT RUNTIME RULES
-----------------------
- state.BTT.entities is authoritative during narrative processing.
- Story-card manual edits are imported only during preflight, before narrative
  processing begins for a transaction.
- Every admitted entity receives exactly four BTT-managed cards: Anatomy,
  Appearance, Instant-Change, and AI-Facing.
- NPC AI-authored appearance refreshes are disabled. Only the Player can receive the
  tagged AI appearance refresh task.
- AI-authored Developable Risk discovery is OFF by default and must be enabled in
  Configure BTT by the scenario creator.
- Creator-authored Developable Risk cards are never automatically rewritten by the
  AI-authoring subsystem. AI-generated risks may extend their own existing tracks or
  add independently qualified new tracks.

PACKAGE CONTENTS
----------------
BTT2.0_RC1.txt
  Complete non-truncated runtime script.

BTT2.0_Standard_Profile_Cards.json
  Nine standard Gender profiles plus Human Heritage.

CREATOR_GUIDE.txt
  Practical scenario-authoring workflow.

STORY_CARD_REFERENCE.txt
  BTT story-card types, ownership, and supported profile formats.

DEVELOPABLE_RISK_GUIDE.txt
  Creator-authored and optional AI-authored Developable Risk grammar/behavior.

CONFIGURATION_REFERENCE.txt
  Complete Configure BTT setting reference.

CHANGELOG.txt
  Public-facing release changes.

RELEASE_NOTES.txt
  RC1 scope, compatibility notes, and known release boundaries.

examples/
  Minimal creator-facing examples.

validation/
  Automated release-candidate audit report and supporting test output.

PROGRAMMER COMMENTS
-------------------
There is intentionally no separate "Programming Notes" document. Technical code
notes live next to the code they explain inside BTT2.0_RC1.txt. Comments are written
to describe responsibility, data flow, invariants, parser grammar, and non-obvious
implementation constraints rather than development history or design-process notes.
