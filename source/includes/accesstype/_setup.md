# Setup

In order to Integrate Razorpay with accesstype, one needs to sign up for Razorpay account and get the  API key and API Secret

You can get these keys by going to Razorpay dashboard -> Settings -> API Keys

After successful generation of API key and Secret, One needs to update those keys in the payment gateway section of Access type

A webhook URL which will present in the Payment Gateways section of Accesstype, needs to be copied and must be in put in webhooks of Razorpay

You need to enable to enable the following events in webhooks

For better security if you want to use the webhook secret of Razorpay, make sure to have the same secret in Razorpay and Accesstype(which can configured at payment gateways)

* subscription.charged
* payment.authorized
* payment.halted
