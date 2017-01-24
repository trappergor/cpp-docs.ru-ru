---
title: "Флаги управления | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "куча отладки, флаги управления"
  - "флаги, элемент управления"
  - "выделение кучи, флаги управления"
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Флаги управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отладочная версия библиотеки времени выполнения Майкрософт C использует следующие флаги для управления процессом выделения памяти в куче и докладывающим процессом.  Дополнительные сведения см. в разделе [Техники отладки CRT](../Topic/CRT%20Debugging%20Techniques.md).  
  
|Flag|Описание|  
|----------|--------------|  
|[\_CRTDBG\_MAP\_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Сопоставляет основные функции кучи и их отладочные версии|  
|[\_DEBUG](../Topic/_DEBUG.md)|Разрешает использование отладочных версий функций среды выполнения.|  
|[\_crtDbgFlag](../Topic/_crtDbgFlag.md)|Контролирует то, как отладочный менеджер кучи отслеживает выделения.|  
  
 Эти флаги можно определить опцией командной строки \/D или с помощью директивы `#define`.  Когда этот флаг определяется с `#define`, директива должна появиться до заголовочного файла, содержащего объявление функций.  
  
## См. также  
 [Глобальные переменные и стандартные типы](../c-runtime-library/global-variables-and-standard-types.md)