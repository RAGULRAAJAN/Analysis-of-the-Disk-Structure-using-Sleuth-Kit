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
![WhatsApp Image 2025-08-13 at 09 18 42_f1739bee](https://github.com/user-attachments/assets/1fd99c6a-91f6-4789-b74b-e7b07c6d320f)



## Create Disk
<img width="642" height="500" alt="Screenshot 2025-08-15 204233" src="https://github.com/user-attachments/assets/d28aee7e-cf2d-4119-a42b-621030809535" />



## mmls

```
mmls disk.dd
```

## fls

```
fls -f fat -o 0 disk.dd
```

<img width="635" height="493" alt="Screenshot 2025-08-15 205431" src="https://github.com/user-attachments/assets/e132eeea-ed29-480d-ae2b-2cffe47c4285" />


<img width="628" height="494" alt="Screenshot 2025-08-15 204732" src="https://github.com/user-attachments/assets/4fcfbc62-20c5-43dc-aba7-7e66b4076c99" />

<img width="631" height="490" alt="Screenshot 2025-08-15 205400" src="https://github.com/user-attachments/assets/b0fefeb9-916f-4e52-bb58-89ab233fa4d1" />


## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
