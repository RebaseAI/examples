[👉🏽 Try Rebase for free, no credit card needed](https://rebase.run)

If you have used AWS, you know about Elastic IPs. These are public IPs you can stick to your EC2 instances, load balancers, or NAT gateways. They let you keep the same public IP, even if you stop and start your resources. This comes in handy if you want to keep your DNS or firewall rules simple.

The thing is, Elastic IPs are not free if you leave them unused. AWS will charge you for any Elastic IP that is not attached to a running resource. If you forget to clean up, your bill goes up for no good reason. Removing unused IPs is one of those things people put off, especially if you have a bunch of them across different regions.

With Rebase, you do not have to mess around in the console or write a script for it. You just give it a prompt and it handles everything for you. Here is how it looks in action.

First, just ask the agent to show you the VPCs and Elastic IPs you have.

![Rebase agent showing a list of VPCs and Elastic IPs in the AWS account](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qwlr14lmxhvif45lpvpa.png)

Now, ask the agent to release all the unassociated Elastic IPs.

![Rebase agent prompt and output showing unassociated Elastic IPs being released](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9316ddn3b9dhb6bqbmw3.png)

That is all it takes.

![Rebase agent showing a confirmation that all unassociated Elastic IPs have been released](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jzwn329qdra8oj1ei9w4.png)

You can check in the AWS Console to confirm they are gone.

![AWS Console showing no unassociated Elastic IPs remaining](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1cz0l2d69smnh9dc8b5h.png)
