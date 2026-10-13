# Third-party sources and attribution

Full Apache-2.0, CC-BY-SA-3.0, and CC-BY-NC-4.0 license texts are provided under
`LICENSES/`. The upstream MIT copyright/license is retained in `upstream/LICENSE`.

PIDS-Bench and baseline/building code: ShirePyDev/Prompt-Injection-Detection-System,
revision 7984e2d6d95e98e914d2b0cd92574b1752614b10. Original copyright and MIT
notice are retained in upstream/LICENSE. Frozen accessible benchmark bytes are
unchanged; upstream/DATA_LICENSES.md describes each source's separate data terms.

Dolly text: Databricks, databricks/databricks-dolly-15k, CC BY-SA 3.0 Unported.
[Dataset card](https://huggingface.co/datasets/databricks/databricks-dolly-15k)
and [license](https://creativecommons.org/licenses/by-sa/3.0/legalcode).
The release extracts instruction fields, filters and selects records, and adds
model scores and operational benign adjudication. Original retained text is
unchanged. Dolly-derived text remains under its source license.

OpenAssistant text: OpenAssistant Conversations (OASST1), Apache-2.0.
[Dataset card](https://huggingface.co/datasets/OpenAssistant/oasst1)
and [license](https://www.apache.org/licenses/LICENSE-2.0).
The release extracts English nondeleted root prompter messages, filters and
selects records, and adds scores and operational benign decisions.

IEEEtran class/style: original bundled notices are retained. Published literature
citations and third-party author names identify the cited sources; they are
preserved for attribution. No project-author name, affiliation, contact address,
personal remote, or local user profile is introduced. No new blanket license for
the project code is imposed by this packaging operation.

The public benchmark contains restricted-source placeholders. No withheld LMSYS
conversation text or reconstruction is included. Prediction exports preserve
only the accessible public evaluation texts.
