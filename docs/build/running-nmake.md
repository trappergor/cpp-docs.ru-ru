---
title: "Запуск программы NMAKE | Microsoft Docs"
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
  - "командные файлы"
  - "командные файлы, NMAKE - программа"
  - "программа NMAKE, выполнение"
  - "программа NMAKE, целевые объекты"
  - "файлы ответа, NMAKE - программа"
  - "целевые объекты"
  - "целевые объекты, построение"
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Запуск программы NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## Заметки  
 Программа NMAKE создает только указанные целевые объекты *targets* или первый целевой объект файла makefile, если целевые объекты не заданы.  Первый целевой объект файла makefile может быть [псевдоцелевым объектом](../build/pseudotargets.md), создающим другие целевые объекты.  NMAKE использует файлы makefile, задаваемые с помощью параметра \/F. Если параметр \/F не указан, программа использует файл makefile, расположенный в текущем каталоге.  Если файл makefile не указан, то программа использует правила вывода для построения целевых объектов *targets* командной строки.  
  
 Текстовый файл `commandfile` \(или файл ответов\) содержит ввод командной строки.  Другие вводимые данные могут предшествовать конструкции @`commandfile` или следовать за ней.  Допускается указание пути.  В файле `commandfile` разрывы строк обрабатываются как пробелы.  Макроопределения следует заключать в кавычки, если они содержат пробелы.  
  
## Дополнительные сведения  
 [Параметры NMAKE](../Topic/NMAKE%20Options.md)  
  
 [Tools.ini и NMAKE](../build/tools-ini-and-nmake.md)  
  
 [Коды выхода из NMAKE](../build/exit-codes-from-nmake.md)  
  
## См. также  
 [Справочник по программе NMAKE](../build/nmake-reference.md)