# AFIDA communications wake-up signal

This repository holds a public change marker for a private communications workflow.

The listener checks `signal.json` once per minute. A changed generation prompts a scan through its existing authenticated reader. The marker is advisory and supplies no authority to perform work.

The JSON contains only a format version and an opaque generation value. Message contents and identifiers are retrieved separately through authenticated access.
