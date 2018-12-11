# MRU
A LabVIEW library for automating a Most-Recently-Used list.  Ties a Combo Box to an INI file.

---

# API
### MRU_Create.vi
> Construct the MRU Helper

Reads the MRU list from the INI file and stores it into the Combo Box.  The first entry in the MRU List
is also stored in the Combo Box's Value for ease of use.

| Parameter | Description |
| --- | --- |
| MRU INI file | Path to the INI file that will hold the MRU values (can be shared with other settings) |
| MRU Section Name | Section in which to store the MRU values |
| CmbBox Refnum | Reference to the System Combo Box that will be used to display/enter the MRU values |
| Number to remember | How many values to remember |

### MRU_GetMRUList.vi
> Fetch the list of Most Recently Used items

This routine will directly populate the Combo Box with items from the INI file.  Note that this operation
is already done in MRU_Create. This VI allows for more of a 'revert' function for the MRU list in the
Combo Box.

| Parameter | Description |
| --- | --- |
| reference in | the MRU Object |

### MRU_UpdateMRUList.vi
> Update the list of Most Recently Used items

Pulls the current Value from the Combo Box and updates the MRU List in the INI file.  Duplicate Values
will cause the existing Value in the MRU list to come to the top but will not add a second instance of
that Value into the MRU List.  Empty Values are ignored.

| Parameter | Description |
| --- | --- |
| reference in | the MRU Object |

### MRU_Destroy.vi
> Release Resources and clean up

This releases the DVR reference used to hold the other references.

| Parameter | Description |
| --- | --- |
| reference in | the MRU Object |

---

# Example
> .\MRU\Example\MRU Example.lvproj

This VI gives a quick demonstration about how/where to use the MRU Library.