# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## REQUIREMENTS
- **Operating System**: Windows 10/11 or Kali Linux
- **Tools**:  
  - [The Sleuth Kit for Windows](https://sleuthkit.org/)  
  - Optional GUI: [Autopsy Forensic Browser](https://www.autopsy.com/)
- **Test Data**: Disk image file (`disk.dd`, `disk.img`, `.E01`)

## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Disk Image / Physical Disk] --> B[mmls - Partition Analysis]
    B --> C[fsstat - File System Metadata]
    C --> D[fls - File Listing]
    D --> E[icat - File Recovery]
    E --> F[Recovered Data / Metadata Report]
```
## DESIGN STEPS:
### Step 1:
- Obtain or create a disk image file (e.g., disk.dd) to analyze.
- Open the terminal in Kali Linux.

### Step 2:
Use Sleuth Kit tools like:
 - mmls → Examine the partition layout.
 - fsstat → View file system details.
 - fls → Get file listing.
 - icat → Recover files using inode numbers.
### Step 3:
Interpret the output to understand:
 - Partition table layout
 - File system metadata (block size, creation time, etc.)
 - Deleted and allocated files
 - Inode-based file recovery

## PROGRAM:
Sleuth Kit Disk Analysis Commands
### Partition Analysis
```bash
mmls disk.dd
```
### File System Metadata
```bash
fsstat -o 2048 disk.dd
```
### File Listing
```bash
fls -o 2048 disk.dd
```
### File Recovery
```bash
icat -o 2048 disk.dd 4 > recovered_file.txt
```
- Recovers the file associated with inode 4.
## SAMPLE WORKFLOW (Windows)
```bash
# Step 1: View partitions
mmls.exe C:\forensics\disk.dd

# Step 2: View file system details
fsstat.exe -o 2048 C:\forensics\disk.dd

# Step 3: List files
fls.exe -r -o 2048 C:\forensics\disk.dd

# Step 4: Recover a file
icat.exe -o 2048 C:\forensics\disk.dd 6 > C:\forensics\image.jpg
```
## OUTPUT:
Disk Structure Analysis Results

<img width="1032" height="257" alt="Screenshot 2025-08-17 184707" src="https://github.com/user-attachments/assets/9e5de96d-d861-42c6-b6fd-681c3b786080" />
<img width="1033" height="487" alt="Screenshot 2025-08-17 184723" src="https://github.com/user-attachments/assets/21ed3a11-6f22-4230-8f56-b3c88c996c32" />
<img width="674" height="313" alt="Screenshot 2025-08-17 184735" src="https://github.com/user-attachments/assets/07a27f32-9e3b-4d12-9c50-5cd321bdd733" />
<img width="1032" height="648" alt="Screenshot 2025-08-17 184744" src="https://github.com/user-attachments/assets/d3d6e8f8-6c05-44bc-aa7f-3ce0a41bf0ba" />

<img width="722" height="303" alt="Screenshot 2025-08-17 184757" src="https://github.com/user-attachments/assets/faaef342-f455-40ab-b1bb-d1e034bdc5c3" />
<img width="635" height="480" alt="Screenshot 2025-08-17 184808" src="https://github.com/user-attachments/assets/d30b7bbb-e23c-41bd-bb48-648e376d5d32" />










## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
