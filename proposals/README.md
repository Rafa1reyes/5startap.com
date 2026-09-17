# Client proposals

`/proposals/` asks for a code. The page hashes what is typed - SHA-256 of
`5startap:proposal:v1:` + CODE (uppercased, spaces and dashes removed) - and fetches
`/proposals/p/<hash>.html`. Wrong code: no such file, 404, "no proposal matches".
The codes never appear anywhere in the site; only their hashes, as filenames.

To add a proposal: pick a code, compute the hash the same way, save the proposal
HTML as `proposals/p/<hash>.html`, and email the code to the client.

    python -c "import hashlib;print(hashlib.sha256(('5startap:proposal:v1:'+'YOURCODE').encode()).hexdigest())"

`robots.txt` disallows `/proposals/p/` and every proposal page carries
`<meta name=robots content=noindex,nofollow>`. GitHub Pages does not list
directories, so the folder cannot be browsed.

Active codes are kept OUT of this repo. They live with Rafael and in the
project notes for each client.
