# Oracle Globally Distributed AI Database: Raft-base Replication FastLab

Welcome to this **LiveLabs FastLab** workshop.

LiveLabs FastLab workshops give you clear, step-by-step instructions to help you quickly gain hands-on experience with the Oracle AI Database. You will go from beginner to confident user in a short time.

Estimated Time: 30 minutes

# Introduction

## About Raft Replication

Oracle Globally Distributed Database provides built-in fault tolerance with Raft replication, a capability that integrates data replication with transaction execution in a sharded database. Raft replication enables fast automatic failover with zero data loss.

![Raft introduction](images/raft-intro.png " ")

[Introduction and verify Lab environment](videohub:1_c5e1jhps)

### Objectives
In this workshop, you will gain first-hand experience in utilizing the Raft Replication within Oracle Globally Distributed Database.

- Testing the use-cases via Podman containers, RAFT UI Application.
- Hands-on Lab for RAFT Topology via GDSCTL which is The command-line utility used to manage and configure Oracle Global Data Services (GDS).
- Exploring the dynamics of Raft.

### Prerequisites
This lab assumes you have:
- An Oracle Free Tier or Paid Cloud account
- Oracle Cloud tenancy (Free Tier, Paid, or LiveLabs reservation)
- Provisioned Raft replication sandbox from the companion workshop stack
- Watch the video for a quick walk through of the Prepare Setup lab.

[Prepare Lab Setup](youtube:DTIGmlj7Y3I)


### Video Walkthrough

[Demo App for Raft Replication](videohub:1_147isows)


## Task 1: Confirm the Remote Desktop Environment

1. Launch your LiveLabs desktop session. By default, two browser windows open: the Introduction on the left and the **RAFT Replication LiveLabs Demo: All Customers List** app on the right.

    ![LiveLabs desktop layout](./images/default_windows_raft_livelabs.png " ")

2. If the windows are not visible, open a terminal from the desktop (Activities → Terminal) and re-run the helper script:

    ```bash
    <copy>
    .livelabs/init_ll_windows.sh
    </copy>
    ```

3. Wait for the browser tabs to reload, then verify that both the overview page and the application tab are active.

## Task 2: Explore the Raft-based replication - Demo UI Application

1. Focus the **RAFT-based Replication LiveLabs Demo: All Customers List** tab or navigate to `http://localhost:8080` if needed.

    ![Customers list](./images/all_customer_after_inital_workload.png " ")

2. Review the pagination controls and the total customer count. The dataset is queried through the catalog service, demonstrating proxy routing across shards.

3. Use the **Add Customer** link to create a sample customer. Confirm that the list refreshes automatically and the total count increases.

4. Optionally exercise **Update** and **Delete** to experience CRUD operations sustained by Raft replication.

## Task 3: Observe Automatic Shard Failover

1. From any customer row, open **More Details** in a new tab to inspect the current shard leader and replication unit for that record.

2. Use the page controls to shut down the leader shard (for example, **Shutdown Shard2**) and wait for the operation to finish.

    ![Shard leadership change](./images/more_details_after_shutdown_shard2.png " ")

3. Monitor the **More Details** view. Raft automatically elects a new leader and re-routes traffic with no manual intervention needed.

4. Return to the main list and continue browsing or performing CRUD operations to validate application continuity.

5. When you are ready, start the shard again with the matching **Start Shard** control to restore full capacity.

## Conclusion

***Congratulations***, you have successfully completed the FastLab on working with the Oracle Globally Distributed AI Database: Raft-base Replication! In this lab, you discovered how to connect demo UI application for Raft-base replication, browse it contents, shutdown a shard database and still see application working since another shard is service the data for the same Replicaion Units.  With these skills, you’ve built the foundation that how to use Raft-based Replication with Oracle Globally Distributed AI Database for Resilient Never Down Apps.

With these skills, you can now help the team replicate new data faster in backgroud while Application data being served from Oracle Globally Distributed AI Database. Visit our Signature Workshop to see more complex examples and learn even more skills.

## Signature Workshop

Ready to explore the complete environment build-out? Continue with the full workshop here: [Use Raft Replication with Distributed Database for Resilient Never Down Apps](https://livelabs.oracle.com/pls/apex/f?p=133:180:::::wid:3772).

## Learn More

- [Raft Replication Documentation](https://docs.oracle.com/en/database/oracle/oracle-database/23/shard/raft-replication.html)
- [Oracle Globally Distributed AI Database Overview](https://www.oracle.com/database/distributed-database/)

## Acknowledgements
- **Authors** – Ajay Joshi, Oracle Globally Distributed AI Database Product Management
- **Contributors** – Edgard Ambler, Shefali Bhargava, Carmen Berdant 
- **Last Updated By/Date** – Ajay Joshi, Oracle Globally Distributed AI Database Product Management, February 2026