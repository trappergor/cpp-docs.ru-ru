---
title: "Предупреждение средств компоновщика LNK4237 | Microsoft Docs"
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
  - "LNK4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4237"
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указан параметр \/SUBSYSTEM:NATIVE при импорте из "библиотека DLL"; используйте \/SUBSYSTEM:CONSOLE или \/SUBSYSTEM:WINDOWS.  
  
 Параметр [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) задан при построении приложения Win32, в котором непосредственно используются один или несколько из следующих компонентов:  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   одна из библиотек DLL msvcrt\*  
  
 Чтобы устранить это предупреждение, не указывайте параметр **\/SUBSYSTEM:NATIVE**.