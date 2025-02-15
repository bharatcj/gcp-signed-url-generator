### Google Cloud Signed URL Generator

A Python script that generates **signed URLs** for files stored in **Google Cloud Storage**, allowing temporary access without exposing credentials.

## 🚀 Features
- **Search files** in Google Cloud Storage using **phone number and timestamp**.
- **Generate signed URLs** for temporary file access (default: **1 hour**).
- **Secure access** to files without exposing storage credentials.
- **Formatted JSON output** for easy integration with other applications.

---

## 🔧 **Installation**

### **1. Install Python and Required Libraries**
Ensure Python is installed. If not, download it from [Python.org](https://www.python.org/downloads/).

Then, install the required dependencies:

```sh
pip3 install google-cloud-storage
```

---

### **2. Configure Google Cloud API**
To use Google Cloud Storage, follow these steps:

1. **Go to Google Cloud Console**: [Google Cloud Console](https://console.cloud.google.com/)
2. **Enable APIs**:
   - Go to **APIs & Services > Enable APIs & Services**.
   - Search for and enable:
     - **Cloud Storage API**
3. **Create a Service Account**:
   - Go to **APIs & Services > Credentials**.
   - Click **Create Credentials > Service Account**.
   - Fill in the details and click **Done**.
4. **Generate a JSON Key File**:
   - Click on the created service account.
   - Go to **Keys** and click **Add Key > Create New Key**.
   - Select **JSON** and download the file.
   - Save it in the project folder as `service_account.json`.

---

## 🎯 **Running the Script**
### **Step 1: Clone the Repository**
```sh
git clone https://github.com/bharatcj/gcp-signed-url-generator.git
cd gcp-signed-url-generator
```

### **Step 2: Set Up Google Credentials**
Set the environment variable for authentication:

#### **Windows (CMD)**
```sh
set GOOGLE_APPLICATION_CREDENTIALS="C:\path\to\service_account.json"
```

#### **Mac/Linux**
```sh
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service_account.json"
```

### **Step 3: Run the Script**
```sh
python3 google_cloud_storage.py <bucket_name> <folder_path> <search_term>
```
Replace:
- `<bucket_name>`: Google Cloud Storage bucket name.
- `<folder_path>`: Folder inside the bucket.
- `<search_term>`: A string (e.g., **phone number + timestamp**) to find the file.

**Example:**
```sh
python3 google_cloud_storage.py my-bucket recordings 1234567890_20240215
```

---

## ⚠️ **Error Handling**
If an error occurs:
- The script prints a **detailed error message**.
- It verifies **search terms** before querying the bucket.
- Returns **formatted JSON responses** for easy debugging.

---

## 🔄 **Customization**
- Modify `google_cloud_storage.py` to change the **signed URL expiration time** (default: **1 hour**).
- Adjust **search logic** to match custom file naming conventions.

---

## 🛡️ **License**
This project is licensed under the **MIT License**.

---

## 🤝 **Contributing**
Contributions are welcome! Feel free to **fork this repository** and submit pull requests.

---

### **Author**
Developed by **Bharat CJ**  
GitHub: https://github.com/bharatcj

---

💡 **Did you know?** Google Cloud **signed URLs** provide **temporary, time-limited access** to your files, meaning you can securely share them without making them public! 🔒🚀