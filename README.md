# kinesis-to-s3

Application for copying Amazon Kinesis data to S3.

## Usage

1. [Download the app](TODO)
2. Configure your application (start with the template `KinesisToS3.SAMPLE.properties`)
3. Configure AWS access credentials:
    1. Locally, set either
        1. the environment variables `AWS_ACCESS_KEY_ID=xxx` and `AWS_SECRET_KEY=yyy`
        2. or the JVM options `-Daws.accessKeyId=xxx` and `-D=aws.secretKey=yyy`
    2. On Amazon EC2
        1. No configuration needed if you start the server instance with a proper IAM role (highly recommended!)
4. Run the app: `java -jar kinesis-to-s3-[version].jar configuration.properties`

## Development

Checkout the source using Git. Initialize the `amazon-kinesis-connectors` submodule using `git submodule update --init --recursive`

The main class is `com.github.codeflows.aws.KinesisToS3`

### Building

Build with [Maven](http://maven.apache.org/). Running

    mvn package
will create a runnable jar at `./target/kinesis-to-s3-[version].jar`

## Notes

Uses the [Amazon Kinesis Client Library](https://github.com/awslabs/amazon-kinesis-client)
and the [Amazon Kinesis Connector Library](https://github.com/awslabs/amazon-kinesis-connectors).

See ["Building a Kinesis application"](http://docs.aws.amazon.com/kinesis/latest/dev/kinesis-record-processor-implementation-app.html) for more details.

The [Kinesis Connector sample code](https://github.com/awslabs/amazon-kinesis-connectors/tree/master/src/main/samples)
is pretty complex, this project does one simple thing.
