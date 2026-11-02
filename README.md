# EX - 02 Analysis of the Disk Structure using Sleuth Kit
## NAME: AKASH G
## REG NO: 212224100004
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


<img width="625" height="410" alt="lab 2 photo 1" src="https://github.com/user-attachments/assets/d8494076-30a7-42ec-bd77-b9904fbf660c" />
<img width="518" height="461" alt="lab 2 photo 2" src="https://github.com/user-attachments/assets/ad792ff1-b6d5-489b-906f-05d6858fad0f" />
<img width="637" height="462" alt="lab 2 photo 3" src="https://github.com/user-attachments/assets/c7e4e0ce-a898-412d-afd7-ac9ba8f156cf" />
<img width="637" height="458" alt="photo 4" src="https://github.com/user-attachments/assets/7f3645fa-88fe-4567-ae9c-9b7c62c5482f" />
<img width="629" height="456" alt="photo 5" src="https://github.com/user-attachments/assets/aa7a9aad-5905-4867-b3a9-38ea8b1c5e59" />
<img width="529" height="442" alt="photo 6" src="https://github.com/user-attachments/assets/fdf06254-03d3-4f78-9f71-eacc12681fd0" />
<img width="487" height="451" alt="photo 7" src="https://github.com/user-attachments/assets/1895b331-b841-44c1-9d5d-b9f4807adbf7" />
<img width="422" height="450" alt="photo 8" src="https://github.com/user-attachments/assets/76fcfb24-47ad-4132-a05d-6d1ea1ba9861" />
<img width="423" height="217" alt="photo 9" src="https://github.com/user-attachments/assets/ebff455a-a117-4ad4-aa6e-d88639c593c9" />

## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
