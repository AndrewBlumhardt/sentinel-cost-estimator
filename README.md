# Sentinel Cost Estimator

From experience to estimation: a practical Microsoft Sentinel cost estimator built from years of real-world deployments.

## Why this exists

Estimating Sentinel cost can become overly complex. This tool is designed to keep focus on the decisions that materially impact spend:

- Ingestion volume
- Pre-ingestion filtering
- Retention strategy
- Long-term storage path (Archive or SDL)
- Growth and budget planning

The estimator is intentionally practical, not perfect. It helps teams move from assumptions to a defensible forecast quickly.

## Background

The model reflects implementation patterns observed across commercial and government environments, from small organizations to large enterprises. It is based on years of Sentinel delivery, training, and optimization work.

## What this app models

The estimator is a single HTML app with no build step. It models:

- Forecast ramp to full ingestion
- Annual increase or decline in volume
- Commitment tier and ingest pricing impact
- Interactive retention period
- Long-term retention via Archive or SDL
- Connector-level filtering percentages
- Connector-level SDL routing percentages
- Defender for Servers effect on SecurityEvent billability
- Budget policy for restore/query operations (modeled as 5% and growth-linked)

## Practical guidance built into the app

- Start from Company Profile presets, then replace with real values.
- Use Best Practices as a baseline when planning a first pass.
- Treat E5 and Defender for Servers as separate cost levers.
- Use filtering deliberately on lower-value/high-volume sources.
- Route only appropriate datasets to SDL.
- Keep enough interactive retention to support fast investigations.

## Recommended workflow

1. Pick the closest company profile.
2. Set users, servers, licensing, and forecast horizon.
3. Adjust ramp and annual growth assumptions.
4. Tune connector filtering and SDL routing percentages.
5. Compare scenarios with Set Baseline and Clear Compare.
6. Export PDF for stakeholder review.

## Accuracy note

The best estimator input is still real telemetry:

1. Enable a connector.
2. Run for several days (ideally one week).
3. Measure actual volume.
4. Refine filtering and routing decisions.

Use this tool for directional planning and decision support. Validate final values with tenant-specific configuration and current regional pricing.

## Files

- `sentinel-cost-calculator.html` - complete estimator (UI, model, charting)

## Run

Open `sentinel-cost-calculator.html` in any modern browser.

## References

- Microsoft Sentinel pricing: https://azure.microsoft.com/pricing/details/microsoft-sentinel/
- Azure Monitor pricing: https://azure.microsoft.com/pricing/details/monitor/

## Disclaimer

This estimator provides practical guidance only. It is not a contractual pricing guarantee. Always confirm against official Microsoft documentation and your tenant-specific data.
