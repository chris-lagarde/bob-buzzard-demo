# bob-buzzard-demo
demo of steps to keep a demo org alive via bob buzzard blog post

Maintenance

After a Salesforce Password Change If Salesforce requires you to reset your password, the stored authentication will become invalid and the workflow will fail. To fix it:

Get a fresh auth URL (use JSON output to avoid terminal formatting issues): sf org display --target-org YOUR_ORG_ALIAS --verbose --json In the JSON output, locate the sfdxAuthUrl value. Update the GitHub secret: Go to this repo's Settings → Secrets and variables → Actions → update the relevant secret with the new auth URL. Re-run the workflow to confirm it passes.

Troubleshooting If you see errors like command not found or exit code 127 in the authentication step, it usually means the secret is empty, malformed, or contains line breaks. Regenerate the auth URL using the JSON method above.
