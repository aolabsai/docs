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

> 🚧 Sending Links
>
> If you are sending `candidate_txt` please be sure the text string includes any hyperlinks from the original resume; [here's a python example of text extraction code that preserves hyperlinks](https://gist.github.com/mi3law/7c5368a27e4ba14092779de810263e1b). Alternatively, you can send relevant links in the `candidate_info` object.

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
