---
title: "Ошибка средств компоновщика LNK1277 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1277"
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка средств компоновщика LNK1277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

запись объекта не найдена в PGD \(имя файла\)  
  
 При использовании [\/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md) путь к одному из входных LIB\-, DEF\- или OBJ\-файлов отличается от пути, который использовался для \/LTCG:PGINSTRUMENT.  Причиной может быть изменение переменной среды LIB после применения \/LTCG:PGINSTRUMENT.  Полный путь к входным файлам хранится в PGD\-файле.  
  
 Параметр \/LTCG:PGOPTIMIZE требует, чтобы входные параметры совпадали с параметрами этапа \/LTCG:PGINSTRUMENT.  
  
 Чтобы устранить это предупреждение, выполните одно из следующих действий.  
  
-   Запустите \/LTCG:PGINSTRUMENT, повторно выполните тесты, после чего запустите \/LTCG:PGOPTIMIZE.  
  
-   Присвойте переменной среды LIB значение, которое она имела при запуске \/LTCG:PGINSTRUMENT.  
  
 Для устранения ошибки LNK1277 не рекомендуется использовать \/LTCG:PGUPDATE.