# Export iPhone contacts and iMessage threads

On a Mac, turn a contacts VCF plus the local iMessage database into one JSON folder per person. Group chats are skipped. The exporter keeps one-to-one threads and can write an anonymized copy for later review. The command and flags live in `data_aggregation/contacts_exporter.py`.

The Electron folder is the [electron-react-boilerplate](https://github.com/electron-react-boilerplate/electron-react-boilerplate) template. It is not the exporter. The root `requirements.txt` lists FastAPI, SQLAlchemy, and spaCy, which the exporter does not import.

## Export a VCF

Grant Terminal Full Disk Access. Install [imessage-exporter](https://github.com/ReagentX/imessage-exporter) (`cargo install imessage-exporter`).

```bash
pip install vobject python-dateutil emoji
cd data_aggregation
python contacts_exporter.py path/to/contacts.vcf --min-messages 10
```

With no path, it looks for a `.vcf` in the current directory. The default minimum is documented in `data_aggregation/README.md`.

No root license is added. The Electron app is someone else's MIT boilerplate, and a single copyright line would cover that code too.
