
# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
### Name : RAGUL RAAJAN T
### Reg.No : 212223100043

## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## DESIGN STEPS:
## Step 1:
Obtain or create a disk image file (e.g., disk.dd) to analyze. Open the terminal in Kali Linux.

## Step 2:
Use Sleuth Kit tools like mmls, fsstat, and fls to examine the partition layout, file system details, and file listing.

## Step 3:
Interpret the output of the tools to understand the disk structure, including partitions, sectors, and files.

## PROGRAM:
Sleuth Kit Disk Analysis Commands

✅ Option 1: Create a Sample Disk Image (for Testing)

Let’s create a 10MB blank disk image and simulate file system activity:

```
cd ~/Downloads

# Step 1: Create an empty disk image
dd if=/dev/zero of=disk.dd bs=1M count=10

# Step 2: Format it with a file system (like FAT32)
mkfs.vfat disk.dd
```

## OUTPUT:
<img width="1195" height="427" alt="Screenshot 2025-09-06 165424" src="https://github.com/user-attachments/assets/03fc9889-d66e-483f-aa62-504ce2a78641" />




## Create Disk

<img width="1191" height="643" alt="image" src="https://github.com/user-attachments/assets/b0a353a9-7c2b-4cc9-89ed-c3a5edc63f1a" />



## mmls

```
mmls disk.dd
```

## fls

```
fls -f fat -o 0 disk.dd
```

<img width="1187" height="245" alt="image" src="https://github.com/user-attachments/assets/03045454-505f-456a-a2cc-09283849d985" />

<img width="1170" height="694" alt="image" src="https://github.com/user-attachments/assets/5f1fa5e2-3099-4309-a583-0ebe994a7d2e" />

<img width="1186" height="585" alt="image" src="https://github.com/user-attachments/assets/9dec2166-4fee-417f-a969-1cdcb9f46b81" />


## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
