---
title:  Identra API Reference
excerpt: >-
  Send a resume or candidate information to receive a fraud likelihood score percentage (0-100%)
api:
  file: ao_core.json
  operationId: identra
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---

Send in the candidate's resume text to receive a fraud assessment from Identra.

`candidate_txt` and `candidate_raw` are mutually exclusive. `candidate_raw` should be the base64 encoding of a 'pdf' or 'docx' file and sent alongside the `raw_resume_type` argument.

```bash
# A curl request using candidate_raw might look something like this
# but with proper request type, url, and headers like you'd see in
# the language example sidebar
B64_ENCODED=$(base64 -i resume.pdf)
curl ...
      --data '
{
  "candidate_raw: "'$B64_ENCODED'",
  "raw_resume_type: "pdf"
}
'
```
