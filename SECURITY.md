# Security policy

Splatfold treats project source as input data while building: it reads files,
tokenizes them, parses their ASTs, renders source, and compile-checks the result.
It does not import or execute project modules during this process.

This does not make generated programs safe to execute. Running a generated
file executes the included project code with the caller's normal Python
permissions.

Local wildcard imports may intentionally resolve through configured roots,
search paths, and relative parent packages. Callers processing untrusted source
trees should therefore control those paths and inspect the dependency list
before using or executing an artifact.

Security reports should use the repository's private security-advisory channel
once the Splatfold repository is published. Do not disclose a suspected
vulnerability in a public issue before a private report has been assessed.

