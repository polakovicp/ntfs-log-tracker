# Notice [2015-04-02] #
# (Note : The latest version is can be downloaded in https://sites.google.com/site/forensicnote/ntfs-log-tracker) #

  * This tool can parse $LogFile, $UsnJrnl of NTFS.
  * A input of this tool is sample file extracted by another tool like Encase, Winhex.
  * If you want to see "Full Path" information, you should input $MFT file.
  * A time information is local time.(system's time)

## Parsed $LogFile Event ##
  1. Creating File/Directory(including "File System Tunneling")
  1. Writing Resident/NonResident Data
    * Writing Resident Data : "Data offset" means the location of Resident Data within $LogFile.
    * Writing Non-Resident Data : "Cluster Number" means "StartClusterNumber(Allocated Cluster Count)" of Non-Resident Data within volume.
  1. Deleting File/Directory
  1. Renaming File/Directory
  1. Moving File/Directory

## Parsed $UsnJrnl Event ##
  1. Event Info : http://msdn.microsoft.com/en-us/library/aa365722.aspx
  1. File Attribute : http://msdn.microsoft.com/en-us/library/gg258117.aspx

## Update History ##
  * v1.4
    * $UsnJrnl record carving function is added
    * Search function is changed.(to only selected columns)
    * Non-English keyword search is supported.
    * Tab bug is fixed
  * v.1.32
    * The bug of Parsing $LogFile is fixed.
  * v.1.31
    * The bug of Parsing $LogFile is fixed.
  * v.1.3
    * The bug of Parsing $UsnJrnl is fixed.
  * v.1.2
    * The bug of Parsing $LogFile is fixed.
  * v.1.1
    * Resizing bug is fixed.
    * The bug of Renaming Event is fixed.(the event of renaming long file name was not extracted.)
    * USN\_RECORD\_V3 is supported.(But in this case, Full Path Information is not supported.)
  * v.1.0
    * Full Screen Mode is supported.
    * Additional information is supported in $LogFile Tab.
      * The "File System Tunneling" Event
      * The target file information on "Writing Data" event
      * The event time on "Deleting File/Directory" and "Renaming File/Directory" event
      * The "Moving File/Directory" event and it's event time
    * The "Source Info" column is added in $UsnJrnl Tab

  * v.0.95
    * "Search Result" Tab is added.
    * Progress Bar is added.
    * The parsed data is saved to SQLite DB.(for Massive Data)

  * v.0.9
    * Initial Version


Created by Junghoon Oh(blueangel), email : blueangel1275@gmail.com