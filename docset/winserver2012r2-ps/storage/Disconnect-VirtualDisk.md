---
external help file: VirtualDisk.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Disconnect-VirtualDisk
description: 
keywords: powershell, cmdlet
author: brianlic
manager: alanth
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D1FD0E42-ED79-41CC-A37A-C9D1A8721ABF
---

# Disconnect-VirtualDisk

## SYNOPSIS
Disconnects a virtual disk from the specified computer, revoking access to the virtual disk.

## SYNTAX

### ByFriendlyName (Default)
```
Disconnect-VirtualDisk [-FriendlyName] <String[]> [-StorageNodeName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Disconnect-VirtualDisk -UniqueId <String[]> [-StorageNodeName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByName
```
Disconnect-VirtualDisk -Name <String[]> [-StorageNodeName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disconnect-VirtualDisk -InputObject <CimInstance[]> [-StorageNodeName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-VirtualDisk** cmdlet disconnects a virtual disk from the specified computer, revoking access to the virtual disk.

To disconnect a virtual disk from a remote computer, from a management node in a subsystem that is registered on the management node, specify the **StorageNodeName** parameter.

## EXAMPLES

### Example 1: Disconnect a virtual disk by friendly name
```
PS C:\>Disconnect-VirtualDisk -FriendlyName VirtualDisk01
```

This example disconnects a virtual disk named VirtualDisk01 from the local machine to prevent futher access to the virtual disk.

### Example 2: Disconnect a virtual disk from a remote computer from a management node
```
PS C:\>Get-StorageSubSystem -FriendlyName "Clustered Storage Spaces on Cluster01" | Get-VirtualDisk -FriendlyName "VDisk01" | Disconnect-VirtualDisk -StorageNodeName "ClustNode1"
```

This command disconnects a virtual disk to from remote computer from a management node in a subsystem that is registered on the management node.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the virtual disk to disconnect.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the VirtualDisk object to disconnect.
Enter a VirtualDisk CIM object, which you can get by using the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual disk to disconnect.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the disconnected virtual disk.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageNodeName
Specifies the name of a computer.
The cmdlet disconnects the virtual disk from the computer that you specify.

Use this parameter only when you run the cmdlet from a management node to disconnect a virtual disk from a remote cluster subsystem.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies the UniqueID of the virtual disk to disconnect.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an array of VirtualDisk objects to the InputObject parameter to specify one or more virtual disks to disconnect.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The Disconnect-VirtualDisk cmdlet does not output objects unless you use the Passthru parameter, in which case it outputs objects that represent the virtual disks that you disconnected.

## NOTES

## RELATED LINKS

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)
