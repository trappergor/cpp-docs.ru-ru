---
title: "Макросы рекурсии | Microsoft Docs"
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
  - "макросы, рекурсия"
  - "программа NMAKE, макросы рекурсии"
  - "макросы рекурсии"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Макросы рекурсии
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Макросы рекурсии используются для рекурсивного запуска программы NMAKE.  Рекурсивные сессии наследуют макросы командной строки и переменных среды, а также сведения из файла Tools.ini.  Правила вывода, определенные в файле makefile, и спецификации **.SUFFIXES** и **.PRECIOUS** не наследуются.  Для передачи макросов рекурсивной сессии NMAKE можно задать переменную среды с помощью оператора SET перед рекурсивным вызовом, определить макрос в команде, осуществляющей рекурсивный вызов, или же определить макрос в файле Tools.ini.  
  
|Макрос|Определение|  
|------------|-----------------|  
|**MAKE**|Команда, изначально использовавшаяся для вызова NMAKE.<br /><br /> Макрос $\(MAKE\) разворачивается в полный путь к файлу nmake.exe.|  
|**MAKEDIR**|Текущий каталог на момент вызова NMAKE.|  
|**MAKEFLAGS**|Действующие в настоящий момент параметры.  Макрос используется в форме `/$(MAKEFLAGS)`.  Обратите внимание, что "\/F" не включается.|  
  
## См. также  
 [Специальные макросы NMAKE](../build/special-nmake-macros.md)