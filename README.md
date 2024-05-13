# Enhanced LevelDB with MVCC and Bulk-Delete Operations

## Introduction
This project aims to enhance LevelDB, a fast key-value storage library developed at Google, by implementing Multi-Version Concurrency Control (MVCC) and bulk-delete operations. These enhancements are designed to improve concurrency control and enable non-blocking reads for transactions, thereby addressing the limitations of LevelDB's original design optimized for single-threaded operations.

## What is MVCC?
Multi-Version Concurrency Control (MVCC) is a database management technique that allows multiple transactions to access the same database concurrently without interference by maintaining multiple versions of data. This approach allows transactions to read older versions of data while another transaction is writing a new version, which improves concurrency and system throughput.

## Project Goals
1. **Implement MVCC**: To enable LevelDB to handle multiple concurrent write operations effectively and support non-blocking reads.
2. **Bulk-Delete Operations**: To introduce efficient mechanisms for removing large numbers of key-value pairs, including:
   - **DeleteAll**: A function to delete all key-value pairs from the database.
   - **BulkDeleteForRange**: A function to delete key-value pairs within a specified key range.
3. **Enhance Query Capabilities**:
   - **GreaterThan**: Allow retrieval of key-value pairs with keys greater than a specified value.
   - **LessThan**: Enable retrieval of key-value pairs with keys less than a specified value.
   - **EqualTo**: Support retrieval of key-value pairs with keys equal to a specified value.
4. **DisplayKeys**: Add a function to display all keys in the database, aiding in database management and debugging.

## Implementation Details
### Multi-Version Concurrency Control (MVCC)
MVCC in LevelDB involves appending a version number or timestamp to each data item. This modification allows each transaction to access a snapshot of the database at a specific point in time, isolating it from changes made by other transactions. This functionality is crucial for enhancing data consistency and reducing lock contention.

### Additional Functionalities
- **DeleteAll and BulkDeleteForRange**: These functions allow for efficient data management, especially in scenarios requiring frequent refreshes or deletions of large data segments.
- **GetLessThan and GetGreaterThan**: These query functions use LevelDB's sorted structure to quickly access ranges of keys, improving the efficiency and flexibility of data retrieval.

## Performance Evaluation
A comprehensive series of tests were conducted to assess the performance impact of MVCC and the newly introduced features in LevelDB. The tests involved mixed read/write queries under varying concurrency levels, from single-threaded up to multi-threaded with five threads.

![Implementation Image 1](Images/MVCC-Flowchart.jpg)
![Implementation Image 2](Images/MVCC-Threads.jpg)
![Implementation Image 3](Images/DeleteAll-Chart.jpg)

## Conclusion
The implementation of MVCC and additional functionalities such as DeleteAll, GetLessThan, and GetGreaterThan within LevelDB has significantly enhanced its performance and capability to handle concurrent operations. These enhancements make LevelDB a more versatile and efficient key-value storage solution for modern applications requiring robust data consistency and efficient handling of concurrent operations.

## Future Work
Further development will focus on overcoming inter-process limitations and incorporating conflict resolution for write operations, thereby extending LevelDB's applicability to more complex transactional environments.

## Collaboration
This project does not provide the source code publicly. However, if you are interested in collaborating or require access to the codebase, please feel free to reach out via email.

## How to Contribute
- If you are interested in contributing to this project, please send an email expressing your interest and outlining your areas of expertise.
- Collaborators will be provided with access to the project's codebase and documentation.

## Contact Information
For further inquiries or collaboration opportunities, please contact:
- Email: glendhingra27@gmail.com

We look forward to potential collaborations and contributions to further enhance the capabilities of LevelDB.

