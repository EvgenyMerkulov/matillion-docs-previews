## Welcome to the documentation for Matillion Unlimited Scale

Unlimited Scale allows a compatible Matillion ETL job to be executed and scheduled via the Matillion SaaS Platform and in a user's data plane by use of an ETL Agent—benefiting from the enhanced scalability capabilities of this new architecture. The data plane and control plane split ensures data sovereignty is adhered to.

### What's a data plane?

This is an abstract concept that ties together an execution environment, for example, AWS Fargate, that uses an ETL Agent. This ETL Agent will be provided by Matillion as a Docker image.

### What's the ETL Agent?

The ETL Agent is the software that executes the job tasks that traditionally run within Matillion ETL. The ETL Agent communicates with the Agent Gateway by an egress-only method. This provides the job tasks, from the SaaS platform, that will be executed. The ETL Agent can scale up by having many instances running concurrently and this can be set based on requirements. There are plans to make this scalable; however, at this moment, they are sized manually or via any cloud provider’s own scaling mechanism. 

### What's the Agent Gateway?

The Agent Gateway is the communication portal that agents will use to communicate with the SaaS Platform. The ETL Agents poll the Agent Gateway for work, as well as send responses for those work tasks.

---

## Considerations

- Matillion Unlimited Scale is presently only available for Matillion ETL for Snowflake (AWS).
- Matillion Unlimited Scale private preview supports a reduced list of components. However, this list will grow over time.
- Matillion will provide you with a specific Matillion ETL instance for Unlimited Scale.
- To run Matillion Unlimited Scale, you must create an ETL Agent. For this to work successfully, you will need to create a number of resources in Amazon Web Services (AWS).
- Matillion will supply a demo job once you are set up with Matillion Unlimited Scale. If this demo job runs successfully, then your Matillion Unlimited Scale instance is connected to your ETL Agent and working as expected.
- Matillion recommends that credentials are stored externally where possible—for example, via AWS Secrets Manager.
- OAuth entries may need to be recreated—such as for Salesforce Query.

Matillion doesn't recommend:

- Running production workloads during the private preview of Matillion Unlimited Scale.
- Running workloads with sensitive data during the private preview period of Matillion Unlimited Scale.

---

## Help us improve Matillion Unlimited Scale

Matillion Unlimited Scale is still in development. Please get in touch with any problems you encounter while using this product.

- More components will be enabled over time.
- If a component is missing and you feel you need it, let us know and we will try to provide a workaround.
- Let us know about any blockers you encounter.
