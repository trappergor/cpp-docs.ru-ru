---
title: "Предупреждение средств компоновщика LNK4104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4104"
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

символ "символ" должен экспортироваться как PRIVATE  
  
 Параметр `symbol` может иметь следующие значения:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 Это предупреждение возникает при построении библиотеки импорта для библиотеки DLL и экспорте одной из перечисленных выше функций без указания ее как PRIVATE в файле определения модуля.  В общем случае эти функции экспортируются только для использования в OLE.  Их размещение в библиотеке импорта может привести к непредвиденному поведению, когда программа, скомпонованная с библиотекой, будет их вызывать.  Дополнительные сведения о ключевом слове PRIVATE см. в разделе [EXPORTS](../Topic/EXPORTS.md).