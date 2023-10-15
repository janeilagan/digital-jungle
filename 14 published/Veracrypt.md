---
aliases: []
tags:
  - published
  - index/21.17
---
# Create a VeraCrypt container

## Step 1: Install VeraCrypt from https://www.veracrypt.fr

## Step 2: Open VeraCrypt and Click `Create Volume`

## Step 3: Selete what type of container you want to create

### Encrypted file container
To create a file as a encrypted container select `Create an encrypted file container`.

### Encrypt a non-system partition
To encrypt a full non-system partion select `Encrypt a non-system partition/drive`. System partition is the partion where system is installed.

## Step 4: Select Encrypted container/volume type

### Standared VeraCrypt volume
Select this option to create normal VeraCrypt Volume.

### Hidden VeraCrypt volume
Select this if you want to create a hidden VeraCrypt volume.

## Step 5: Select the volume location
For `Encrypted file container` select the **file location** and **name** by clicking `Select File...`, and for `Encrypt a non-system partition` select the **device/partion** by clicking `Select Device...` button.

## Step 6: Select Encryption options
Choose encrypt algorithm and hash algorithm. Use the default settings if you are not sure what to select.

## Step 7: Select Volume Size (Only for `Encrypted file container`)
Select the encrypted container size.

## Step 8: Choose a Volume password
In this step enter a password for you encrypted volume. You can also use keyfiles with the password for extra security.

## Step 9: Select Filesystem type
If you use Windows select `NTFS` and for any Linux distribution select `Linux Ext4`.

## Step 10: Cross-Platform Support
Select `I will mount the volume on other platforms` if you want to open the volume in everywhere (Windows and Linux).

## Step 11: Format/Encrypt
Move the mouse corsor inside the VeraCrypt windows until `Randomness Collected From Mouse Movements` get full. After the progress become full then click `Format` to format/create the container.

## Step 12: Click `Exit` to finish the process

---

**Source:** https://www.veracrypt.fr/en/Beginner%27s%20Tutorial.html / https://gist.github.com/ImaginativeShohag/6dca147f85c1ef4219b6be47e54fa287

# Open a VeraCrypt container

## Step 1: Open the "VeraCrypt" folder (extracted from the portable version) and locate the `Veracrypt.exe` file. 

## Step 2: Double click `Veracrypt.exe` to run the file.

## Step 3: Choose a drive letter to mount the container to

## Step 4: Select the file
This is the encrypted file usually `.hc`
## Step 5: Click Mount and input the encrypted drive's password

## Step 6: Open the drive with the files.

## Step 7: Dismount the drive before closing.