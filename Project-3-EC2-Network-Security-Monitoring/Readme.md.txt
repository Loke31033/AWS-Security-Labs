# AWS EC2 Network Security Monitoring & Automated Alerting

## Overview

This project demonstrates a practical AWS network security monitoring and detection pipeline.

The environment uses VPC Flow Logs, Amazon CloudWatch Logs, Metric Filters, CloudWatch Metrics, CloudWatch Alarms, and Amazon SNS to detect and alert on rejected network traffic.

## Objectives

- Monitor EC2 network traffic
- Collect VPC Flow Logs
- Investigate rejected connections
- Create a CloudWatch Metric Filter
- Generate a custom security metric
- Create an automated CloudWatch Alarm
- Send security alerts through SNS
- Investigate network events
- Validate security controls through retesting

## AWS Services

- Amazon EC2
- Amazon VPC
- VPC Flow Logs
- Amazon CloudWatch
- CloudWatch Logs Insights
- CloudWatch Metric Filters
- CloudWatch Alarms
- Amazon SNS
- AWS CloudTrail
- Amazon EventBridge

## Security Scenario

A controlled connection attempt was made against TCP port 23 (Telnet).

The connection was rejected because Telnet was not permitted by the EC2 network security configuration.

The rejected event was captured by VPC Flow Logs and detected through CloudWatch.

## Detection Pipeline

Internet / Client
↓
EC2 / VPC
↓
VPC Flow Logs
↓
CloudWatch Logs
↓
Metric Filter
↓
RejectedTrafficCount
↓
CloudWatch Alarm
↓
SNS Notification
↓
SOC Investigation

## Detection Logic

Filter:

REJECT

Metric:

RejectedTrafficCount

Alarm:

RejectedTrafficAlarm

Threshold:

>= 1 rejected event within 1 minute

## Investigation

The rejected connection was investigated using CloudWatch Logs Insights.

The flow-log evidence identified TCP port 23 as the destination port and showed the traffic action as REJECT.

## Remediation

The EC2 Security Group was reviewed to ensure unnecessary services were not exposed.

SSH TCP/22 remained available for legitimate administration while Telnet TCP/23 remained blocked.

## Security Outcome

The environment successfully demonstrated:

- Network traffic monitoring
- Security event detection
- Automated alerting
- SOC investigation
- Least-privilege network access
- Security validation through retesting

## Skills Demonstrated

- AWS VPC Security
- EC2 Security Groups
- VPC Flow Logs
- CloudWatch
- CloudWatch Logs Insights
- Detection Engineering
- Security Monitoring
- Alert Investigation
- SNS Alerting
- Network Security
- Incident Response
- Least Privilege

## Evidence

Screenshots are provided in the `Screenshots` directory.

Sensitive information such as account identifiers and unnecessary public IP information should be redacted before publishing screenshots publicly.