---
title: "Предупреждение средств компоновщика LNK4070 | Microsoft Docs"
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
  - "LNK4070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4070"
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

директива \/OUT:"имя\_файла" в файле EXP отличается от имени выходного файла "имя\_файла"; директива игнорируется  
  
 Имя файла `filename`, указанное в операторе [NAME](../Topic/NAME%20\(C-C++\).md) или [LIBRARY](../../build/reference/library.md) при создании файла EXP, отличается от выходного имени файла `filename`, использованного по умолчанию или указанного с помощью параметра [\/OUT](../../build/reference/out-output-file-name.md).  
  
 Предупреждение появится при изменении имени выходного файла в среде разработки или если DEF\-файл проекта не был обновлен.  Следует вручную обновить DEF\-файл, чтобы устранить данное предупреждение.  
  
 Проблемы могут возникнуть у клиентской программы, использующей результирующую библиотеку DLL.