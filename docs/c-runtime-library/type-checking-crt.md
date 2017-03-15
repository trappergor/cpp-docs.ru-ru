---
title: "Проверка типов (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проверка типа"
  - "проверка типов"
  - "функции с переменным аргументом"
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Проверка типов (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компилятор выполняет ограниченную проверку типов для функций, которые могут принимать переменное число аргументов, следующим образом:  
  
|Вызов функции|Аргументы для проверки|  
|-------------------|----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Первый аргумент \(строка формата\)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Первые два аргумента \(файл или буфер и строка формата\)|  
|`_snprintf_s`|Первые три аргумента \(файл или буфер, количество и строка формата\)|  
|`_open`|Первые два аргумента \(путь и флаг `_open`\)|  
|`_sopen_s`|Первые три аргумента \(путь, флаг `_open` и режим общего доступа\)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Первые два аргумента \(путь и первый указатель на аргумент\)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Первые три аргумента \(флаг режима, путь и первый указатель на аргумент\)|  
  
 Компилятор выполняет ту же ограниченную проверку типов для аналогов этих функций для расширенных символов.  
  
## См. также  
 [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)