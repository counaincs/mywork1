## PwC Switzerland Cybersecurity Job Simulation - July 2024

- Completed a job simulation involving cybersecurity for PwC Digital Intelligence, gaining experience in understanding and explaining the concept of integrated defense.
- Developed expertise in integrated defense strategies and their application in real-world scenarios.
- Conducted risk assessments and formulated security recommendations for a client.
- Demonstrated proficiency in cybersecurity terminology, network segmentation, and firewall configuration

Risk assessment activity
![Risk Assessment_page-0001](https://github.com/user-attachments/assets/aba80043-b440-4486-a6b1-6f0638d34f51)
![Risk Assessment_page-0002](https://github.com/user-attachments/assets/d949c66d-fef9-4010-adb0-66b44e642e5e)
![Risk Assessment_page-0003](https://github.com/user-attachments/assets/7a0df7c4-d049-4f99-b084-6b37c6b74f34)
![Risk Assessment_page-0004](https://github.com/user-attachments/assets/89273514-27a3-4a8f-a0be-b01c40c2b72f)
![Risk Assessment_page-0005](https://github.com/user-attachments/assets/d5f55bf4-6332-45fd-a059-7687d4176535)
![Risk Assessment_page-0006](https://github.com/user-attachments/assets/4f7e2d25-2954-4ea7-a980-f933370cb487)
![Risk Assessment_page-0007](https://github.com/user-attachments/assets/3d1e97dc-abb4-4103-8f05-a217043af082)
![Risk Assessment_page-0008](https://github.com/user-attachments/assets/5b82b074-1c4c-44e8-be62-8bfe052f149e)
![Risk Assessment_page-0009](https://github.com/user-attachments/assets/1e4ee1d1-d338-4fcd-a18d-405f2455c778)
![Risk Assessment_page-0010](https://github.com/user-attachments/assets/ca50e12a-4317-4683-b070-66f49ed8ee70)

root cause Analysis
![Root Cause Analysis_page-0001](https://github.com/user-attachments/assets/737d2783-b249-4770-a9da-576b1555fed3)

![IT System Security Baseline_page-0001](https://github.com/user-attachments/assets/31f27c84-ed45-4577-af36-5a2963f0dc63)
![IT System Security Baseline_page-0002](https://github.com/user-attachments/assets/03a98922-5f74-4d80-9927-aa80a2f17ec9)
![IT System Security Baseline_page-0003](https://github.com/user-attachments/assets/c07c8b0b-61ec-4d72-bcdc-42ec8e2ec316)

![Network Segmentation Flow_page-0001](https://github.com/user-attachments/assets/dd5e57ff-e24c-4f8f-86e7-84e5f88f2469)

# Introduction to Network Segmentation

Network segmentation is the practice of dividing a computer network into smaller, distinct sub-networks or segments. This is done to improve performance, enhance security, and simplify management. Each segment can be managed and secured separately, which is particularly useful in large, complex networks.

## How Segmentation Contributes to Network Security

1. **Isolation of Critical Assets**
   - **Containment of Threats**: By isolating critical assets (e.g., servers, sensitive data) in separate segments, network segmentation limits the spread of malware or unauthorized access. If a breach occurs in one segment, it does not necessarily compromise other segments.
   - **Access Control**: Segmentation allows for granular access control, ensuring that only authorized users and devices can access specific segments. This reduces the risk of insider threats and unauthorized access.

2. **Enhanced Monitoring and Detection**
   - **Focused Monitoring**: Segments can be monitored individually, making it easier to detect suspicious activity or anomalies. Security teams can focus their efforts on high-risk areas, improving the chances of early threat detection.
   - **Reduced Noise**: By segmenting the network, the volume of data that needs to be monitored is reduced, decreasing false positives and allowing for more efficient security operations.

3. **Improved Incident Response**
   - **Faster Containment**: In the event of a security incident, segmentation allows for quicker containment of the threat. Security teams can isolate affected segments to prevent the spread of malware or unauthorized access.
   - **Streamlined Investigation**: Investigating security incidents becomes easier with segmentation, as the scope of the investigation is limited to specific segments. This allows for more efficient and thorough forensic analysis.

4. **Compliance and Regulatory Requirements**
   - **Meeting Standards**: Many regulatory frameworks (e.g., GDPR, PCI-DSS) require organizations to implement network segmentation to protect sensitive data. Compliance with these standards is often mandatory for avoiding penalties and ensuring business continuity.
   - **Audit Facilitation**: Segmented networks make it easier to demonstrate compliance during audits, as specific segments can be shown to meet regulatory requirements.

## How Segmentation Enhances Organizational Security

1. **Operational Efficiency**
   - **Reduced Attack Surface**: By segmenting the network, the overall attack surface is reduced. Attackers have fewer entry points, making it more difficult for them to gain unauthorized access.
   - **Resource Optimization**: Network segmentation allows for the efficient use of security resources. Security measures can be prioritized and applied where they are most needed, improving overall security posture.

2. **Scalability and Flexibility**
   - **Scalable Security**: As organizations grow, network segmentation allows for scalable security measures. New segments can be created as needed, without compromising the security of existing segments.
   - **Adaptability**: Segmented networks can be adapted to changing business needs. For example, new segments can be created for temporary projects or specific departments, allowing for flexible and dynamic security management.

3. **Enhanced Collaboration**
   - **Cross-Functional Teams**: Different segments can be managed by cross-functional teams, fostering collaboration between IT, security, and business units. This ensures that security measures are aligned with business objectives.
   - **Targeted Training**: Security awareness training can be tailored to the needs of specific segments, improving the overall security culture within the organization.

---

# Configuring Firewalls at Boldi AG

Boldi AG has defined the following network segments:
- **Domain**: A namespace which logically divides an organisation’s network objects that share the same directory.
- **Admin Zone**: Special purpose server zone, e.g., central logging, Security Information and Event Management (SIEM).
- **Server Zone**: General purpose server zone, e.g., application servers, database servers.
- **Client Zone**: General purpose client zone, e.g., user laptops.

## Firewall Configuration Approaches

There are two primary approaches to configuring firewalls: whitelisting and blacklisting.

1. **Whitelisting (Allow-Listing)**
   - Only explicitly allowed traffic is permitted. All other traffic is denied by default.
   - This approach provides a high level of security, as it minimizes the chances of unauthorized access.

2. **Blacklisting (Deny-Listing)**
   - Explicitly denies traffic from known malicious sources or unwanted destinations. All other traffic is allowed by default.
   - This approach is less secure than whitelisting, as it relies on identifying and blocking known threats, which may not be comprehensive.

## Firewall Configuration at Boldi AG

1. **Firewall A (Between Domain and Admin Zone)**
   - **Approach**: Whitelisting
   - **Configuration**: Only allow necessary traffic from the Domain to the Admin Zone. This includes directory services traffic and any specific administrative tasks that need access to the Admin Zone.
   - **Reason**: The Admin Zone contains critical security infrastructure (e.g., SIEM). It is essential to strictly control access to minimize the risk of unauthorized access and potential compromise of security management systems.

2. **Firewall B (Between Admin Zone and Server Zone)**
   - **Approach**: Whitelisting
   - **Configuration**: Only allow traffic required for administrative tasks and monitoring from the Admin Zone to the Server Zone. This includes traffic for logging, monitoring, and security management.
   - **Reason**: The Server Zone contains important application and database servers. Limiting access to only necessary administrative traffic helps protect these critical assets from unauthorized access.

3. **Firewall C (Between Server Zone and Client Zone)**
   - **Approach**: Whitelisting
   - **Configuration**: Only allow necessary traffic from the Client Zone to the Server Zone, such as specific application traffic and database queries required for client operations.
   - **Reason**: The Client Zone consists of user laptops, which are more likely to be compromised. Restricting access to only necessary traffic reduces the risk of potential attacks spreading from the Client Zone to the Server Zone.

4. **Firewall D (Between Client Zone and External Network)**
   - **Approach**: Blacklisting (with additional whitelisting)
   - **Configuration**: Block known malicious traffic and unnecessary services from the external network while allowing essential client traffic (e.g., web browsing, email).
   - **Reason**: The Client Zone interacts with the external network. Blacklisting known threats helps protect client devices, while whitelisting essential services ensures business operations are not disrupted.

## Conclusion

Network segmentation significantly enhances network security by isolating critical assets, improving monitoring, and facilitating incident response. Configuring firewalls using a combination of whitelisting and blacklisting ensures robust protection tailored to the specific needs of each network segment. These measures collectively contribute to the overall security posture of Boldi AG, safeguarding its assets and operations from potential threats.


