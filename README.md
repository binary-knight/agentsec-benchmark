# agentsec-benchmark

Opt-in sandbox measurements from [agentsec-pack](https://github.com/binary-knight/agentsec-pack). It measures how much a coding agent's sandbox lets a process reach: its privileges, network, secrets, filesystem and other processes. No figures are published yet.

## Submit a measurement

```bash
agentsec probe --label my-run --how "what you ran it under" --redact
agentsec submit reports/my-run.json --agent "agent name" --agent-version 1.2.3 --sandbox "the mode, in the agent's words"
```

`agentsec submit` needs a version of agentsec-pack newer than 0.3.0. It prints the exact record and asks at the terminal, then opens a pre-filled issue here that you read and post yourself. It sends nothing on its own.

A record holds the agent, its version, the sandbox mode and any settings you list, the OS family, the probe version, the state of each of the five axes, the finding IDs and the score. It holds no hostnames, paths or usernames. Words that look like a path, a variable name or a name from your machine are refused.

**Posting is public.** The issue, your GitHub account and the record are visible to anyone, and the threshold below does not change that.

## What gets published

Figures come from `agentsec benchmark`:

- A configuration appears once **5 different GitHub accounts** have submitted it. A configuration is the agent, version, sandbox mode, settings, OS family and probe version.
- Each account counts once per configuration, using its newest record.
- A figure is a median score, the most common state of each axis, and the number of accounts behind it.
- Results reproduced by the maintainer or a known harness are shown apart from community submissions, and each says where it came from.

Submissions are not checked against a re-run, so a community figure reports what accounts posted. An issue labeled `rejected` is not counted.

## License

The records are released under [CC0 1.0](LICENSE). Posting a record releases it under the same terms.
