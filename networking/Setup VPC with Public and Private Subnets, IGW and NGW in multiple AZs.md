Every app on AWS needs a network setup that just works. You want your web servers out in the open, but your databases safe and locked away. That’s why people set up a VPC with both public and private subnets, spread across a few zones, with the right gateways so traffic moves how it should.

Setting this up in AWS is harder than it sounds. You miss one step, pick the wrong subnet, or forget a route, and things break. Your servers might not talk to the internet, or worse, you end up exposing your database.

Rebase makes this part easy. Instead of clicking through AWS or messing with templates, you just say what you want, and Rebase handles the rest. Here’s what it looks like.

Once you’re logged in and done with onboarding, you’ll land on the homepage.

![Rebase app homepage after onboarding](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nyybuseq1blhi17jzg7x.png)

We have a few prompts ready to go, and we’re adding more. If you pick “VPC with public and private subnets”, the prompt fills in for you.

![Prompt for VPC with public and private subnets](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uyok5kwyl9dax2o8s6jw.png)

The agent will check with you before doing anything.

![Agent asking for confirmation before proceeding](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wij0wc1xsexrkl2i50bb.png)

If you want something specific, just say so. You can mention a CIDR block or any detail you care about. If you want Rebase to figure it out, just leave it to the agent.

![User providing specific VPC details](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lomr33eijewsrgn9iil4.png)

Rebase will share what it plans to do and will ask you to approve it.

![Agent sharing final plan and asking for approval](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d0tniz021pwyth4uk1xy.png)

Once you give the green light, it gets started.

![Provisioning starting after approval](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ck7jnk311yxr5mmjnwp6.png)

For every action that changes something, Rebase will always ask you first. You get three options:

```yaml
Yes: Proceed
No: Cancel
Feedback: Tell the agent to change something or do it differently. For example, you might say, actually use just one AZ.
```

![Explicit permission request for each mutating action](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gz0q9qggdvaj4xh4qz9q.png)

You can turn off these permission checks anytime from the workspace settings.

![Workspace settings showing explicit permission toggle](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/t5bx52s92wqedsau5eb5.png)

Rebase will build out everything, and if it hits something new, it will check with you first.

![Agent asking for user input on new decisions](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/aufudiefi91eubtov55a.png)

When it’s done, you’ll see a summary of what the agent did, step by step.

![Summary of actions the agent took](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7ffqil7xe0l2bwwjx6ki.png)

That’s it. The stuff that usually eats up hours or days, Rebase does it for you in a few seconds.

You can always double check in AWS to see everything is there.

![AWS console showing provisioned resources](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/okcaq153lzt2sbvh2vag.png)

The tags are there too, just like you asked for.

![Tags added to AWS resources](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ils8fx4ytte3vuz2hqrc.png)

You can also ask Rebase what this setup is going to cost you every month. The agent will break down all the main parts that AWS charges for, show you what’s free, and give you a ballpark number. You can even get a detailed estimate based on how much traffic or data you expect.

This is useful if you’re trying to keep your AWS bill in check or just want to know what to expect before you hit deploy.

![Agent giving detailed AWS cost estimate for VPC setup](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5r8gh12m52g9m3jhpb7e.png)