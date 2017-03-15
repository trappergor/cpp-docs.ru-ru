---
title: "Неустранимая ошибка C1382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1382"
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Неустранимая ошибка C1382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PCH\-файл "файл" был перестроен с момента создания "объект".Повторите построение этого объекта  
  
 В процессе компиляции с использованием параметра [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) обнаружен PCH\-файл, имеющий более новую версию, чем OBJ\-файл CIL, в котором содержится указатель на него.  Сведения в OBJ\-файле CIL устарели.  Выполните повторное построение объекта.  
  
 Ошибка C1382 также возникает во время компиляции с параметром **\/Yc**, если компилятору передается несколько файлов исходного кода.  Чтобы устранить эту ошибку, не используйте параметр **\/Yc** при передаче компилятору нескольких файлов исходного кода.  Для получения дополнительной информации см. [\/Yc \(создать предварительно скомпилированный заголовочный файл\)](../../build/reference/yc-create-precompiled-header-file.md).