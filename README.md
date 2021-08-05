<p align="center">
  <img src="https://github.com/khero1212/CloudFormation_WebApp/blob/master/header.jpg" alt="header" />
</p>

<br>

## High Availability Web Application using AWS CloudFormation

Infrastructure-as-code (IAC) that automates the process of creating a secured and high-availability environment and deploying an application (packaged and staged in AWS S3 Storage) into a dockerized Apache Web Server. The script contains all the configurations needed for a repeatable process so that the infrastructure can be discarded and recreated at will multiple times.

<br>

### Architecture Overview

<img src="https://github.com/khero1212/CloudFormation_WebApp/blob/master/Diagram.png" alt="diagram"/>

### Launch Configuration Specifications

`1.`  Load-balanced servers with auto-scaling capability across two availability zones within a single region.

`2.`  Server/instance specification: 2vCPUs, 4GB RAM, 10GB EBS disk volume.

`3.`  Linux Operating System using the Ubuntu 18 distribution based Amazon Machine Image (AMI).

`4.`  EC2 instances are secluded in a private subnet and only accepts incoming traffic from a NAT gateway and load-balancer, both within a public subnet.

`5.`  Load-balancer and web application servers have security groups defined with only specific ports enabled.

`6.`  Web Application servers have outbound internet access via NAT gateway to serve the users with files.

`7.`  Sample application code is packaged and stored in an S3 bucket with IAM permissions.

`8.`  Application servers are configured with IAM instance profile to be able to access and download application code from AWS S3 bucket.

`9.` Application code is deployed in a dockerized apache web server for added security and isolation.

`10.` Health checks and thresholds are defined to aid in system availability detection.  Metrics are collected, aggregated, and monitored via AWS CloudWatch.

`11.` Entire environment is fully virtualized in a cloud platform that can be taken down and brought back up within a short period of time. The process of creating and starting all the services, spinning up instances are automated via scripts in this repo.

<br>