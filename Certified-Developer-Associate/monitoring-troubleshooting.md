# Monitoring and Troubleshooting

## CloudWatch

### Alarms

* Alarm metric duration should be equal to or greater than the frequency of the metric monitoring that you want to alarm on.
  - Basic monitoring for EC2 provides metrics every 5 minutes
  - Detailed monitoring provides metrics every 1 minute
  - High-Resolution metrics provide metric data ever 10 to 30 seconds.

* Alarms can invoke a notification to Amazon SNS or an Auto Scaling policy. Action is only taken on _sustained_ state changes.

* There is a higher charge for high-resolution alarms
