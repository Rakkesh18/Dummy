Here's how you can update the **Pipeline Overview** section to include the two pipelines:

---

### **3. Pipeline Overview**

#### **3.1 Pipeline Objectives**
The primary objective of the disaster recovery pipelines is to automate critical tasks to ensure quick recovery during a disaster. This involves two key pipelines:
- **Resource Provisioning Pipeline:** Automates the deployment of infrastructure resources required to restore the STIB application.
- **Database Restoration Pipeline:** Restores the database with the latest backup to ensure data continuity.

#### **3.2 How the Pipelines Work**

- **Resource Provisioning Pipeline:**
  - **Step 1:** Trigger Detection: This pipeline is triggered based on predefined conditions or manual activation in response to a disaster.
  - **Step 2:** Resource Deployment: The pipeline provisions the necessary infrastructure resources using predefined templates (e.g., ARM templates, Bicep scripts).
  - **Step 3:** Configuration and Testing: Configures the deployed resources and runs validation tests to ensure everything is functioning correctly.
  - **Step 4:** Notification: Sends notifications to relevant stakeholders once the deployment is complete.

- **Database Restoration Pipeline:**
  - **Step 1:** Trigger Detection: This pipeline is activated after the Resource Provisioning Pipeline completes or based on predefined disaster recovery conditions.
  - **Step 2:** Backup Retrieval: Retrieves the latest backup of the STIB application database from the storage account.
  - **Step 3:** Database Restoration: Restores the database to the newly provisioned SQL managed instance in the secondary region.
  - **Step 4:** Validation: Runs checks to ensure the database is restored correctly and is operational.
  - **Step 5:** Notification: Sends notifications to relevant stakeholders once the database restoration is successful.

#### **3.3 Pipeline Triggers and Conditions**
The pipelines can be triggered by various conditions, such as:
- Detection of a critical failure in the primary infrastructure.
- Manual initiation in response to a disaster.
- Scheduled tests or simulations to verify the disaster recovery plan.

---

This update clearly defines the roles of the two pipelines in the disaster recovery process, emphasizing their specific objectives and the steps they follow to ensure a smooth recovery.
