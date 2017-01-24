---
title: "Эквиваленты собственным типам C++ в .NET Framework (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], эквиваленты C++"
ms.assetid: 7f116a9a-26cd-46db-9877-a63ffdc88723
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Эквиваленты собственным типам C++ в .NET Framework (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В приведенной ниже таблице представлены ключевые слова для встроенных типов Visual C\+\+, которые являются псевдонимами предопределенных типов в пространстве имен **System**.  
  
|Тип Visual C\+\+|Тип платформы .NET Framework|  
|----------------------|----------------------------------|  
|**bool**|**System.Boolean**|  
|**signed char** \(дополнительные сведения см. в разделе [\/J](../build/reference/j-default-char-type-is-unsigned.md)\)|**System.SByte**|  
|**unsigned char**|**System.Byte**|  
|**wchar\_t**|**System.Char**|  
|**double** и **long double**|**System.Double**|  
|**float**|**System.Single**|  
|**int**, **signed int**, **long** и **signed long**|**System.Int32**|  
|**unsigned int** и **unsigned long**|**System.UInt32**|  
|**\_\_int64** и **signed \_\_int64**|**System.Int64**|  
|**unsigned \_\_int64**|**System.UInt64**|  
|**short** и **signed short**|**System.Int16**|  
|**unsigned short**|**System.UInt16**|  
|**void**|**System.Void**|  
  
## См. также  
 [Управляемые типы](../Topic/Managed%20Types%20\(C++-CLI\).md)