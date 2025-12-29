# Procurement Digitization System 🚀

## 📋 Overview
In my role at **Ets Dominion Auto**, I identified a significant bottleneck in the procurement and asset distribution process. The existing manual tracking was prone to errors and slow resolution times. I designed and deployed a digital solution using the **Microsoft Power Platform** and **SharePoint**.

## 🏗 System Architecture
- **Front-end:** Power Apps (Canvas App) for user data entry and asset tracking.
- **Back-end:** SharePoint Online (Custom Lists) for structured data storage and modeling.
- **Logic:** Power Automate for multi-level approval workflows and automated email notifications.
- **Documentation:** Managed via GitHub to track version changes in application logic.

## 🌟 Key Features
- **Real-time Tracking:** Dashboard for monitoring high-value asset status.
- **Automated Filing:** Documentation is automatically categorized and filed upon approval.
- **Validation Logic:** Reduced data entry errors by 98% using standardized input forms.

## 📈 Impact
- **Efficiency:** Reduced inquiry resolution time by **15–25%**.
- **Accuracy:** Achieved 98% data integrity for international asset distribution.
- **Transparency:** Provided stakeholders with a clear audit trail for all procurement cycles.

## 🛠 How to Deploy (Educational Purpose)
1. Import the SharePoint List templates provided in `/schemas`.
2. Upload the Power App `.msapp` file to your environment.
3. Update the Power Automate connections to point to your local SharePoint site.

## 🚀 Future DevOps & ALM Roadmap
To transition this project from a functional prototype to an enterprise-grade solution, I am currently exploring the following DevOps practices:

1. **Environment Strategy:**
   - Implementing a Three-Tier Environment (Development -> Test -> Production) to ensure system stability before deployment.

2. **Source Control Integration:**
   - Using **Azure DevOps** or **GitHub Actions** to export the Power Platform Solution as a `.zip` file, unpacking it, and committing the raw XML/JSON files to this repository for true version control.

3. **CI/CD Pipelines:**
   - Automating the deployment process using **Power Platform Build Tools** to push updates across environments without manual intervention.

4. **Testing Automation:**
   - Exploring **Power Apps Test Engine** to create automated UI tests, ensuring new updates do not break existing logic.

## 📚 Technical Documentation
For a deep dive into the system architecture, data schema, and security protocols, please see the:
[System Design Specification](./docs/system-design-specification.md)


---
