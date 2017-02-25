---
title: "Ошибка средств компоновщика LNK2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2027"
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка средств компоновщика LNK2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Неразрешенная ссылка модуля "модуль"  
  
 Файл, переданный компоновщику, зависит от модуля, который не был задан с помощью параметра **\/ASSEMBLYMODULE**, равно как и не был передан непосредственно компоновщику.  
  
 Чтобы устранить ошибку LNK2027, выполните одно из следующих действий:  
  
-   Не передавайте компоновщику файл, который зависит от модуля.  
  
-   Задайте модуль с помощью параметра **\/ASSEMBLYMODULE**.  
  
-   Если модуль безопасное .netmodule, передайте модуль непосредственно компоновщику.  
  
 Дополнительные сведения см. в разделах [\/ASSEMBLYMODULE \(добавление модуля MSIL в сборку\)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) и [.NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md).