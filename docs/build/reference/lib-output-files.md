---
title: "Выходные LIB-файлы | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "выходные файлы, LIB"
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Выходные LIB-файлы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выходные файлы, создаваемые LIB, зависят от используемого режима, как показано в следующей таблице.  
  
|Режим|Output|  
|-----------|------------|  
|По умолчанию \(создание или изменение библиотеки\)|Библиотека COFF \(.lib\)|  
|Извлечение члена с помощью ключа \/EXTRACT|Объектный файл \(.obj\)|  
|Создание файла экспорта и библиотеки импорта с помощью ключа \/DEF|Библиотека импорта \(.lib\) и файл экспорта \(.exp\)|  
  
## См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)