# AFIDA communications wake-up signal

This repository holds a public change marker for a private communications workflow.

The listener checks `signal.json` once per minute. A strictly newer generation prompts a scan through its existing authenticated reader. Older or equal cached values remain quiet. The marker is advisory and supplies no authority to perform work.

The JSON contains exactly `version` (1) and `generation` (32 lowercase hexadecimal characters). The publisher advances a durable 128-bit counter; consumers compare fixed-width hexadecimal strings exactly, retain a never-decreasing watermark and run only one scan at a time. Completion must not erase newer pending work. The polling interval is not a delivery-time guarantee.

Message contents, identifiers and receipts are retrieved separately through authenticated access. No private message data or credentials belong in this repository.
