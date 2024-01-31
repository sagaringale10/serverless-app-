# serverless-app-
// index.js

exports.handler = async (event) => {
  console.log("Received S3 event:", JSON.stringify(event, null, 2));

  // Extract relevant information from the S3 event
  const bucket = event.Records[0].s3.bucket.name;
  const key = event.Records[0].s3.object.key;

  console.log(`File uploaded to bucket: ${bucket}, key: ${key}`);

  // Your business logic can go here

  return {
    statusCode: 200,
    body: JSON.stringify("File processed successfully"),
  };
};
