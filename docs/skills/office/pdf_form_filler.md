# PDF Form Filler Skill

**ID**: `office/pdf_form_filler`
**Issuer**: [@rosspeili](https://github.com/rosspeili) ([@ARPAHLS](https://github.com/ARPAHLS))
<!-- skill-doc-meta:begin -->
- **Version**: `0.1.0` — 16 Jul 2026
<!-- skill-doc-meta:end -->
<!-- skill-intent:begin -->
**Solves:** Map natural-language fill instructions onto AcroForm PDF fields for document automation.
**Works with:** Gemini, Claude, OpenAI, DeepSeek, Ollama, and Bedrock-compatible host loops.
**Runtime:** Needs `ANTHROPIC_API_KEY` for the semantic field mapper.
<!-- skill-intent:end -->

**Recommended install:** `pip install "skillware[office_pdf_form_filler]"`. See [Install extras](../../usage/install_extras.md).
[Skill Library](../README.md) · [Office](README.md) · [Testing](../../TESTING.md)

A productivity skill that fills AcroForm-based PDFs by mapping natural language instructions to detected form fields using semantic understanding.

## Capabilities

*   **Smart Field Detection**: Automatically identifies text fields, checkboxes, radio buttons, and dropdowns in standard PDFs.
*   **Semantic Mapping**: Uses an internal LLM (Claude) to understand user instructions (e.g., "Sign me up for the newsletter") and map them to the correct field (e.g., `checkbox_subscribe_newsletter`).
*   **Context Awareness**: Extracts nearby text labels to ensure accurate mapping, even if field names are obscure (e.g., `field_123` vs label "First Name").
*   **Type Safety**: Automatically converts values to the correct format (booleans for checkboxes, specific options for dropdowns).

## Bundle layout

The skill is self-contained in `skills/office/pdf_form_filler/`. [Skill anatomy](../../introduction.md#skill-anatomy). Vocabulary: [glossary](../../glossary.md). **Contract** — see Manifest Details above. **Assurance** — `test_skill.py` in the bundle.

### Directive (`instructions.md`)
