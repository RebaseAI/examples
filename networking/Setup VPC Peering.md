
[👉🏽 Try Rebase for free, no credit card needed](https://rebase.run)

If you work with multiple VPCs in AWS, sooner or later you’ll want them to talk to each other. Sometimes you split workloads into different VPCs to keep things separate, or your team is working across different AWS accounts. AWS lets you connect those VPCs with something called VPC peering. That way, the traffic stays private, never hitting the public internet. But if you’ve ever tried to set this up by hand, you know it can be a hassle. You have to make sure the CIDR blocks do not overlap, the route tables are right, and both sides accept the connection. Missing one step means your setup just doesn’t work.

With Rebase, you can do all of this just by telling the agent what you want. Here’s how it works from start to finish.

We’ll start by spinning up two VPCs, both with private subnets and non-overlapping CIDR blocks. This is important, because VPC peering won’t work if the address ranges clash.

![This screenshot shows two separate VPCs with their own private subnets and unique CIDR blocks. The network diagrams are side by side.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bxch3txb51te8gze7w7h.png)

The AI agent will put together a plan and show you exactly what it’s about to do. If it needs more info, it’ll ask before moving ahead.

![Here, the agent prompts for any extra details it needs to finish building the plan, like subnet ranges or region.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8d5nxb2gefsgh4988agf.png)

Once you answer, the agent finalizes the plan for you.

![This step displays the full breakdown of what’s going to be created in AWS.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sgxjypztr8bbkfjfn8we.png)

The agent asks for a quick confirmation to make sure everything looks right.

![The agent displays a confirmation message, waiting for your approval.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ami159k439ry8qh6yqfg.png)

After you confirm, the agent goes ahead and provisions everything.

![The UI shows that resources are being created and progress updates as it moves through the steps.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yfum4v9feq76ibhgcybe.png)

When it’s done, you’ll get a summary of everything it created. You can see all the details here.

![Summary screen with the new VPC IDs, subnets, and other details.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/43s7lia7tofo519fpb52.png)

Now grab those VPC and subnet IDs. Let’s try connecting to an EC2 instance in one of these VPCs using AWS SSM (Session Manager).

![Here, the screenshot highlights EC2 instance details, showing where to find instance IDs and SSM status.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/i0wsxi5cnipzqx236xvi.png)

When you tell the agent you want to access EC2 via SSM, it will ask for confirmation and take care of the setup.

![The UI confirms that it’s about to set up the IAM permissions and any prerequisites needed for SSM.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zvqlheh9txvidnegqbs0.png)

After it’s done, it will let you know that everything is set up and ready.

![Screenshot shows SSM access has been configured successfully.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/65lx72cu0w9road8ll55.png)

You’ll see the exact commands you need to connect through AWS SSM.

![Screen with copy-paste ready commands to connect to your EC2 instances using SSM.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ks1o995pvi3hqb103jcg.png)

If you hit any errors, just tell the agent and it will troubleshoot and fix things for you.

![Screenshot shows the agent working through and resolving a user-reported problem.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/po0tkcgz20xk82smmfe8.png)

It’ll walk you through any follow-up steps if you need more help.

![Agent is showing additional instructions or info on the screen.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3mve3g6kklzehzqjgb2q.png)

![Another example of the agent breaking things down for you.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/94kn3erl935iy9c3zl5a.png)

Now, grab the private IPs of both instances in each VPC. You’ll need them for the next step.

![The EC2 dashboard displays private IP addresses for each running instance.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ic3xqdlsicg84ptqlwlu.png)

If you’re not sure how to test the setup, just ask the agent and it’ll help out.

![Screen displays suggested ways to check connectivity, like ping commands.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f264gzir7aa1lfoj6f54.png)

When you log in with SSM and try to ping the other instance from the first one, it won’t work yet. That’s because VPC peering isn’t enabled.

![Screenshot shows a ping command timing out, showing the two VPCs are not connected yet.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/m562oat77g6ujspjmtx7.png)

Now, let the agent know you want to enable VPC peering. It will handle everything needed for that.

![Screen shows the agent starting the VPC peering setup.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cxutbah4bkbm2yxiqref.png)

The agent figures out all the steps, including updating route tables, so traffic can flow between the VPCs.

![Here, it shows the agent updating routes and confirming peering is enabled.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dsuqa3dsy3cf6v1slkzq.png)

If there’s anything else needed, the agent will suggest it and ask for your go-ahead.

![Screenshot with a confirmation prompt for additional changes.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ekarls2xrv5g8yaxq9ay.png)

When it’s all done, you’ll get a summary of what was changed.

![Screen shows a summary of the peering connection and updated route tables.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xp9cycbwu031jjcb1ljr.png)

If you want to double-check, you can confirm everything from the AWS console.

Here’s the VPCs:

![Screenshot shows the AWS VPC dashboard with both VPCs and the peering connection.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lvoqr4kipw9s8hhzfjhr.png)

And here’s the EC2 instances:

![EC2 dashboard with both instances running in separate VPCs.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/azmctrdroam228umryxj.png)

Now, if you try pinging from one EC2 instance to the other over their private IPs, it works. You’re all set.

![Screenshot shows a successful ping from one instance to the other after peering is complete.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7xth2ck0ab5gzkov56f6.png)

That’s it. VPC peering, start to finish, without having to mess with the AWS console or memorize all the steps.
