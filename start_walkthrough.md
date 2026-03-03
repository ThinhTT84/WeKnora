# Walkthrough: Colima Setup Configuration

I have provided a recommended Colima configuration to support the WeKnora project's heavy database and processing services.

## Advice Provided

For an **arm64 Mac**, I recommended the following command to ensure sufficient resources (4 CPUs, 8GB RAM, 100GB Disk) and optimized file system performance (`vz`/`virtiofs`):

```bash
colima start --cpu 4 --memory 8 --disk 100
```

## Significance
This configuration avoids common performance bottlenecks and out-of-memory errors when running the full WeKnora stack, specifically:
- **ParadeDB (Postgres)**: Needs enough memory for vector search.
- **DocReader**: Requires CPU overhead for OCR and parsing tasks.
- **Persistent Data**: 100GB disk ensures plenty of space for Docker images and project data.

## Next Steps
1. Execute the command in your terminal.
2. Once Colima is ready, use the newly translated script to start the project:
   ```bash
   ./scripts/start_all_en.sh
   ```
