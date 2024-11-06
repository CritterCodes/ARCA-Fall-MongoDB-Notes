### **Guide: Setting Up MongoDB Locally**

---

#### **Step 1: Download MongoDB**

1. **Visit the MongoDB Download Center**  
   Go to [MongoDB's official download page](https://www.mongodb.com/try/download/community) and select your operating system.

2. **Choose the Correct Package**  
   - For Mac/Linux: Download the `.tgz` (tarball) file.
   - For Windows: Download the `.zip` file instead of the `.msi` installer to avoid setting up MongoDB as a service.

#### **Step 2: Extract the Downloaded Files**

1. **Locate the Downloaded File**  
   - For Mac/Linux: Locate the `.tgz` file in your `Downloads` folder and extract it by double-clicking.
   - For Windows: Extract the `.zip` file by right-clicking and selecting "Extract All."

2. **Navigate to the Extracted Folder**  
   Inside the extracted folder, locate the `bin` directory. This folder contains the MongoDB binaries, including `mongod` (MongoDB daemon) and `mongo` (MongoDB shell).

#### **Step 3: Create a Data Directory**

MongoDB requires a directory to store its data.

1. **Open Terminal or Command Prompt**  
2. **Navigate to the Extracted Directory**  
   Change to the `bin` directory inside the extracted folder:
   ```bash
   cd /path/to/your/mongodb/bin
   ```

3. **Create a Directory for MongoDB Data**  
   Run the following command to create a directory called `mongodb_data`:
   ```bash
   mkdir -p mongodb_data
   ```

#### **Step 4: Start the MongoDB Server**

1. **Run MongoDB Daemon with a Custom Data Path**  
   Start the MongoDB server with a command that specifies the data directory created above:
   ```bash
   ./mongod --dbpath /path/to/your/mongodb_data
   ```

2. **Verify Server is Running**  
   You should see log messages in the terminal indicating MongoDB is listening on `localhost` and ready for connections.

3. **Note the Port (Default is 27017)**  
   By default, MongoDB runs on port `27017`. This is where you’ll connect from the MongoDB shell or other tools.

#### **Step 5: Connect to MongoDB Locally (Optional)**

To interact with MongoDB, you can use either the MongoDB shell or MongoDB Compass.

- **Using Mongo Shell**: In a new terminal window, run:
  ```bash
  ./mongo
  ```
  This connects to the running MongoDB instance on `localhost:27017`.

- **Using MongoDB Compass** (Graphical Interface):
  - Download and install MongoDB Compass from [MongoDB Compass Download Page](https://www.mongodb.com/try/download/compass).
  - Open Compass and connect to `localhost:27017`.

#### **Step 6: Stop MongoDB When Done**

When finished, you can stop MongoDB by pressing `CTRL + C` in the terminal running `mongod`.
