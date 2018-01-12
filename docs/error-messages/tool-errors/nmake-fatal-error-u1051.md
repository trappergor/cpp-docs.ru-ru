---
title: "Неустранимая ошибка NMAKE U1051 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1051
dev_langs: C++
helpviewer_keywords: U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93c109bf723b3c4cf08e998a715fe8f6f33be466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1051"></a>Неустранимая ошибка NMAKE U1051
Недостаточно памяти  
  
 NMAKE не хватило памяти, включая виртуальной памяти, поскольку файл makefile слишком большой или сложной.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Освободите место на диске.  
  
2.  Увеличьте размер файла подкачки Windows NT или файл подкачки Windows.  
  
3.  При использовании часть файла makefile только разделите makefile отдельные файлы или использовать **! Если** директивы для ограничения объема, который должен обрабатывать NMAKE препроцессора. **! Если** директивы содержат **! Если**, `!IFDEF`, **! Ifndef:**, **! ELSE IF**, **! ELSE** `IFDEF`, и **! ELSE** `IFNDEF`.