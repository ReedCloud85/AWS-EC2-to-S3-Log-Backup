# AWS-EC2-to-S3-Log-Backup
AWS EC2 to S3 Log Backup lab with IAM permissions and Bash scripting

## Overview
This lab demonstrates automated backups of EC2 logs to S3 using a Bash script and an IAM role with least-privilege access.

## Steps
1. Created an S3 bucket with all public access blocked.
2. Wrote a Bash script (`backup.sh`) to compress `/var/log` and upload to S3.
3. Attached an IAM role that allows `s3:PutObject` and `s3:ListBucket` only on the backup bucket.
4. Ran the script:
   - Without `sudo` → permission errors on restricted logs.
   - With `sudo` → successful backup of all logs.

## Files
- `backup.sh` — Bash backup script
- `BackupPolicy.json` — IAM policy
- Screenshots of terminal output and S3 uploads

## Lessons Learned
- Some logs require root permission to read.
- IAM roles + least privilege help ensure secure automated backups.
