---
title: "Ошибка BSCMAKE BK1503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1503"
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка BSCMAKE BK1503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удалось записать в файл 'filename' \[: причина\]  
  
 BSCMAKE совмещает SBR\-файлы, созданные во время компиляции, в одну базу данных браузера.  Эта ошибка возникает, если размер этой базы данных превышает 64 Мб или если число входных SBR\-файлов превышает 4092.  
  
 Если число SBR\-файлов превышает 4092, необходимо уменьшить их число.  В Visual Studio этого можно добиться, используя параметр [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) для всего проекта и повторной пофайловой проверкой.  
  
 Если размер BSC\-файла превышает 64 Мб, необходимо уменьшить число входных SBR\-файлов, что также снизит размер BSC\-файла.  Кроме этого, объем данных просмотра можно уменьшить, используя параметры \/Em \(исключить символы расширения макросов\), \/El \(исключить локальные переменные\) и \/Es \(исключить системные файлы\).  
  
## См. также  
 [Параметры BSCMAKE](../Topic/BSCMAKE%20Options.md)