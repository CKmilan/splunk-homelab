# Troubleshooting & Notes

## VM Freezes
- Problem: Ubuntu VM was freezing during Splunk indexing.
- Cause: Too few CPU cores and low video memory assigned.
- Fix: Increased CPU cores to 6 and video memory to 160 MB in VirtualBox.

## Display Issue
- Problem: Poor resolution and blurry screen even after setting high resolution.
- Fix: Installed VirtualBox Guest Additions and rebooted. Issue resolved.

## Log Visibility
- Initially no logs appeared under `/var/log`.
- Fix: Used full path with correct permissions:
  ```bash
  sudo /opt/splunk/bin/splunk add monitor /var/log
  ```

## Dashboard JSON refresh
- Manually edited dashboard JSON to set:
  ```json
  "refresh": "60sec"
  ```

## SSH Brute Force Simulation
- Tested failed and successful SSH logins using manual and automated attempts.
- Splunk correctly detected failed logins and repeated IP attempts.
