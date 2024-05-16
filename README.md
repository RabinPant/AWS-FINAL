# AWS-FINAL


# amazon-cloudfront:
```
Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.
```
# amazon-accelerator:
```
Global Accelerator improves performance for a wide range of applications over TCP or UDP by proxying packets at the edge to applications running in one or more AWS Regions. Global Accelerator is a good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP, as well as for HTTP use cases that specifically require static IP addresses or deterministic, fast regional failover. Both services integrate with AWS Shield for DDoS protection.

```
```
BEAN STALK: AWS Elastic Beanstalk simply sets up the infrastructure (EC2 instance, load balancer, auto-scaling group) for your application. It’s a more expensive and a bit of an overkill solution for hosting a bunch of client-side files.



Many companies that distribute content over the Internet want to restrict access to documents, business data, media streams, or content that is intended for selected users, for example, users who have paid a fee. To securely serve this private content by using CloudFront, you can do the following:

– Require that your users access your private content by using special CloudFront signed URLs or signed cookies.

– Require that your users access your Amazon S3 content by using CloudFront URLs, not Amazon S3 URLs. Requiring CloudFront URLs isn’t necessary, but it is recommended to prevent users from bypassing the restrictions that you specify in signed URLs or signed cookies. You can do this by setting up an origin access identity (OAI) for your Amazon S3 bucket. You can also configure the custom headers for a private HTTP server or an Amazon S3 bucket configured as a website endpoint.
```
#### S3
```
Storage Classes
Storage Classes for Frequently Accessed Objects
S3 STANDARD for general-purpose storage of frequently accessed data.
S3 EXPRESS ONE ZONE is a high-performance, single AZ storage class designed to deliver consistent single-digit millisecond data access for frequently accessed data and latency-sensitive applications. It can improve data access speeds by 10x and reduce request costs by 50% compared to S3 Standard and scales to process millions of requests per minute.
Storage Classes for Infrequently Accessed Objects
S3 STANDARD_IA for long-lived, but less frequently accessed data. It stores the object data redundantly across multiple geographically separated AZs.
S3 ONEZONE_IA stores the object data in only one AZ. Less expensive than STANDARD_IA, but data is not resilient to the physical loss of the AZ.
These two storage classes are suitable for objects larger than 128 KB that you plan to store for at least 30 days. If an object is less than 128 KB, Amazon S3 charges you for 128 KB. If you delete an object before the 30-day minimum, you are charged for 30 days.
Amazon S3 Intelligent Tiering
S3 Intelligent-Tiering is a storage class designed for customers who want to optimize storage costs automatically when data access patterns change, without performance impact or operational overhead. 
S3 Intelligent-Tiering is the first cloud object storage class that delivers automatic cost savings by moving data between two access tiers — frequent access and infrequent access — when access patterns change, and is ideal for data with unknown or changing access patterns.
S3 Intelligent-Tiering monitors access patterns and moves objects that have not been accessed for 30 consecutive days to the infrequent access tier. If an object in the infrequent access tier is accessed later, it is automatically moved back to the frequent access tier.
S3 Intelligent-Tiering supports the archive access tier.  If the objects haven’t been accessed for 90 consecutive days, it will be moved to the archive access tier. After 180 consecutive days of no access, it is automatically moved to the deep archive access tier.
There are no retrieval fees in S3 Intelligent-Tiering.
S3 GLACIER
For long-term archive
S3 Glacier provides the following storage classes: S3 Glacier Instant Retrieval, S3 Glacier Flexible Retrieval, and S3 Glacier Deep Archive.
Archived objects are not available for real-time access. You must first restore the objects before you can access them.
You cannot specify GLACIER as the storage class at the time that you create an object.
Glacier objects are visible through S3 only.
Retrieval Options
Expedited – allows you to quickly access your data when occasional urgent requests for a subset of archives are required. For all but the largest archived objects, data accessed are typically made available within 1–5 minutes. There are two types of Expedited retrievals: On-Demand requests are similar to EC2 On-Demand instances and are available most of the time. Provisioned requests are guaranteed to be available when you need them.
Standard – allows you to access any of your archived objects within several hours. Standard retrievals typically complete within 3–5 hours. This is the default option for retrieval requests that do not specify the retrieval option.
Bulk – Glacier’s lowest-cost retrieval option, enabling you to retrieve large amounts, even petabytes, of data inexpensively in a day. Bulk retrievals typically complete within 5–12 hours.
For S3 Standard, S3 Standard-IA, and Glacier storage classes, your objects are automatically stored across multiple devices spanning a minimum of three Availability Zones.
```

