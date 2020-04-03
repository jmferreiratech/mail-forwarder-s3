mail-forwarder-s3
--

You can use Amazon Simple Email Service (SES) to receive (and send) e-mails on addresses at a custom domain (support@example.com).
This setup can be both cheaper and more powerful than using a third-party solution.

This version is an improvement over [the one that uses only SNS (Simple Notification System)](https://github.com/jmarcelof/mail-forwarder-sns)
and as such has a message size limit of 10 MB, much greater than the former (150 KB).

### Before you get your hands dirty
* You need to [verify your domain with Amazon SES](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-domain-procedure.html)
* You have to [publish an MX record for email receiving](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-mx-record.html)

Take in account that all email addresses for which you'll send messages have to be verified or you need to [be out of the SES sandbox](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/request-production-access.html).

### Deploy
The deploy consists of 3 simple steps:
1. Create `config.yml` file (based on `config-template.yml`)
2. Actually deploy it: `$yarn deploy`
3. Activate the SES Rule Set created: `AWS Console > SES > Rule Sets`
