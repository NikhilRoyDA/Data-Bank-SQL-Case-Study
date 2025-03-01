# 📊 SQL Case Study: Data Bank - Neo-Banking Metrics Analysis  

## 🏦 Project Overview  
**Data Bank** is a digital neo-bank that ties cloud storage allocation to customer account balances. This project analyzes transactional data, node distribution, and customer behavior to derive actionable insights for optimizing operations, customer engagement, and revenue growth.  

**Business Goals**:  
- Optimize node network infrastructure.  
- Identify high-revenue regions.  
- Improve customer retention strategies.  

---

## 📂 Schema & Tables  
The database consists of 3 tables:  

### 1. `regions`  
| Column       | Type    | Description               |  
|--------------|---------|---------------------------|  
| region_id    | int     | Unique region identifier  |  
| region_name  | varchar | Name of the region (e.g., Australia) |  

### 2. `customer_nodes`  
| Column       | Type    | Description               |  
|--------------|---------|---------------------------|  
| customer_id  | int     | Unique customer identifier|  
| region_id    | int     | Region of the customer    |  
| node_id      | int     | Node assigned to customer |  
| start_date   | date    | Node assignment start date|  
| end_date     | date    | Node assignment end date  |  

### 3. `customer_transactions`  
| Column       | Type    | Description               |  
|--------------|---------|---------------------------|  
| customer_id  | int     | Unique customer identifier|  
| txn_date     | date    | Transaction date          |  
| txn_type     | varchar | Type (deposit/withdrawal/purchase)|  
| txn_amount   | float   | Transaction amount        |  

---

## 🔍 SQL Queries & Insights  
All queries are stored here : [`SQL_Queries](https://github.com/NikhilRoyDA/Data-Bank-SQL-Case-Study/blob/main/Queries%20%26%20Solutions.sql)

### **Key Questions Solved**  
1. **Unique Nodes in Network**  
   - **Query**: Count distinct nodes.  
   - **SQL Skills**: `COUNT(DISTINCT)`.  
   - **Insight**: 5 unique nodes form the network.  

2. **Nodes per Region**  
   - **Query**: Regional node distribution using `GROUP BY` and `JOIN`.  
   - **Insight**: Australia has the highest node density.  

3. **Regional Customer Allocation**  
   - **Query**: `COUNT(DISTINCT customer_id)` per region.  
   - **Business Impact**: Target underpenetrated regions.  

4. **Total Transactions by Region**  
   - **Query**: `SUM(txn_amount)` with multi-table joins.  
   - **Insight**: Asia contributes 35% of total revenue.  

5. **Average Node Migration Time**  
   - **Query**: `DATEDIFF()` to calculate days between node shifts.  
   - **Insight**: Avg. 15 days to switch nodes.  

6. **Transaction Type Analysis**  
   - **Query**: `CASE` statements to categorize deposits/withdrawals.  
   - **Trend**: Deposits dominate transaction volume (42%).  

7. **Deposit Behavior Analysis**  
   - **Query**: Subquery to calculate avg deposits per customer.  
   - **Insight**: Avg. customer makes 5 deposits/month ($508 each).  

8. **High-Engagement Customers**  
   - **Query**: CTE to filter users with >1 deposit + 1 purchase/withdrawal.  
   - **Business Impact**: 27% of customers are high-engagement.  

---

## 📈 Visuals & Results  
![Transaction Trends](media/transaction_trends.png)  
*Sample result: Transaction distribution by type and region.*  

---

## 🙏 Acknowledgments  
- Mentorship by **Akash Raj Sir** and **CloudyML**.  
- Dataset inspired by real-world neo-banking challenges.  

---

## 🔗 Connect & Explore  
- **Portfolio**: [DataSciencePortfol.io](https://www.datascienceportfol.io/nikhilroy744)  
- **LinkedIn**: [Nikhil Kumar Roy](https://www.linkedin.com/in/nikhil-kumar-roy/)  

---

## 📜 License  
This project is MIT licensed.  

