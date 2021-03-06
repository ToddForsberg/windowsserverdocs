---
title: logman update trace
description: "Windows Commands topic for **** - "
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b7111f7f-4162-4d1a-8e53-d766db0ede1f britw
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
---
# logman update trace

>Applies To: Windows Server (Semi-Annual Channel), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Update the properties of an existing event trace data collector.  
  
## Syntax  
```  
logman update trace <[-n] <name>> [options]  
```  
## Parameters  
|Parameter|Description|  
|-------|--------|  
|/?|Displays context-sensitive help.|  
|-s <computer name>|Perform the command on the specified remote computer.|  
|-config <value>|Specifies the settings file containing command options.|  
|-ets|Send commands to Event Trace Sessions directly without saving or scheduling.|  
|[-n] <name>|Name of the target object.|  
|-f <bin&#124;bincirc&#124;csv&#124;tsv&#124;sql>|Specifies the log format for the data collector.|  
|-[-]u <user [password]>|Specifies the user to Run As. Entering a * for the password produces a prompt for the password. The password is not displayed when you type it at the password prompt.|  
|-m <[start] [stop] [[start] [stop] [...]]>|change to manual start or stop instead of a scheduled begin or end time.|  
|-rf <[[hh:]mm:]ss>|Run the data collector for the specified period of time.|  
|-b <M/d/yyyy h:mm:ss[AM&#124;PM]>|Begin collecting data at the specified time.|  
|-e <M/d/yyyy h:mm:ss[AM&#124;PM]>|End data collection at the specified time.|  
|-o <path&#124;dsn!log>|Specifies the output log file or the DSN and log set name in a SQL database.|  
|-[-]r|Repeat the data collector daily at the specified begin and end times.|  
|-[-]a|append to an existing log file.|  
|-[-]ow|Overwrite an existing log file.|  
|-[-]v <nnnnnn&#124;mmddhhmm>|attach file versioning information to the end of the log file name.|  
|-[-]rc <task>|Run the command specified each time the log is closed.|  
|-[-]max <value>|Maximum log file size in MB or maximum number of records for SQL logs.|  
|-[-]cnf <[[hh:]mm:]ss>|When time is specified, create a new file when the specified time has elapsed. When time is not specified, create a new file when the maximum size is exceeded.|  
|-y|Answer yes to all questions without prompting.|  
|-ct <perf&#124;system&#124;cycle>|Specifies the Event Trace Session clock type.|  
|-ln <logger_name>|Specifies the logger name for Event Trace Sessions.|  
|-ft <[[hh:]mm:]ss>|Specifies the Event Trace Session flush timer.|  
|-[-]p <provider [flags [level]]>|Specifies a single Event Trace provider to enable.|  
|-pf <filename>|Specifies a file listing multiple Event Trace providers to enable. The file should be a text file containing one provider per line.|  
|-[-]rt|Run the Event Trace Session in real-time mode.|  
|-[-]ul|Run the Event Trace Session in user mode.|  
|-bs <value>|Specifies the Event Trace Session buffer size in kb.|  
|-nb <min max>|Specifies the number of Event Trace Session buffers.|  
|-mode <globalsequence&#124;localsequence&#124;pagedmemory>|Specifies the event trace session logger mode.<br /><br />**Globalsequence** specifies that the event tracer add a sequence number to every event it receives irrespective of which trace session received the event.<br /><br />**Localsequence** specifies that the event tracer add sequence numbers for events received at a specific trace session. When the **localsequence** option is used, duplicate sequence numbers can exist across all sessions but will be unique within each trace session.<br /><br />**Pagedmemory** specifies that the event tracer use paged memory rather than the default non-paged memory pool for its internal buffer allocations.|  
## Remarks  
Where [-] is listed, an extra - negates the option.  
## <a name="BKMK_examples"></a>Examples  
The following command updates the existing data collector perf_log, changing the maximum log size to 10 MB, updating the log file format to CSV, and appending file versioning in the format mmddhhmm.  
```  
logman update perf_log -max 10 -f csv -v mmddhhmm  
```  
#### additional references  
[logman](logman.md)  
[logman create trace](logman-create-trace.md)  
