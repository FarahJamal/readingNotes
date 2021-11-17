# Kinesis
![](https://pbs.twimg.com/media/EnUm8bjXYAIks7f.jpg)
- on Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. Amazon Kinesis offers key capabilities to cost-effectively process streaming data at any scale, along with the flexibility to choose the tools that best suit the requirements of your application. With Amazon Kinesis, you can ingest real-time data such as video, audio, application logs, website clickstreams, and IoT telemetry data for machine learning, analytics, and other applications. Amazon Kinesis enables you to process and analyze data as it arrives and respond instantly instead of having to wait until all your data is collected before the processing can begin.

![](https://digitalcloud.training/wp-content/uploads/2018/07/Kinesis-Data-Streams-Architecture.jpg)

**Analytics**
  * Analytics category - enables you to collect analytics data for your App. The Analytics category comes with built-in support for Amazon Pinpoint and Amazon Kinesis.
  * Set up Analytics backend
    - Run the following command in your project’s root folder: amplify add analytics
    - Configure: 
    ? Select an Analytics provider (Use arrow keys)
    `Amazon Pinpoint`
    ? Provide your pinpoint resource name: 
    `yourPinpointResourceName`
    ? Apps need authorization to send analytics events. Do you want to allow guests and unauthenticated users to send analytics events? (we recommend you allow this when getting started) 
    `Yes`
    - Deploy: amplify push

  * Install Amplify Libraries
    dependencies {
    // Add these lines in `dependencies`
    implementation 'com.amplifyframework:aws-analytics-pinpoint:1.17.1'
    implementation 'com.amplifyframework:aws-auth-cognito:1.17.1'
    }

  * Initialize Amplify Analytics - initialize the Amplify Auth and Analytics categories you call Amplify.addPlugin() method for each category. To complete initialization call Amplify.configure().
    - Add the following code to onCreate():
    Amplify.addPlugin(new AWSCognitoAuthPlugin());
    Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));

  * Record Events:
    AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();
    Amplify.Analytics.recordEvent(event);

  * View Analytics console with the following command:
    amplify console analytics

![](https://media.makeameme.org/created/just-use-kinesis.jpg)
