## Auto Scaling Strategy
The application uses an Auto Scaling Group to dynamically adjust capacity based on traffic demand.

## Scaling Policies
- Scale Out:
  - Triggered when average CPU utilization exceeds 70%
- Scale In:
  - Triggered when CPU utilization drops below 30%

## Load Balancing
- Application Load Balancer distributes traffic evenly
- Health checks ensure traffic is sent only to healthy instances

## Fault Tolerance
- Multi-AZ deployment
- Automatic replacement of unhealthy instances
- No single point of failure

## Stateless Design
- EC2 instances are stateless
- Allows seamless scaling and instance replacement

## Performance Benefits
- Handles traffic spikes automatically
- Maintains low latency
- Improves application availability
