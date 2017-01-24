---
title: "Входные LIB-файлы | Microsoft Docs"
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
  - "входные файлы, LIB"
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Входные LIB-файлы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB ожидает те или иные входные файлы в зависимости от режима использования, как показано в следующей таблице.  
  
|Режим|Ввод|  
|-----------|----------|  
|По умолчанию \(создание или изменение библиотеки\)|Файлы объектов COFF \(.obj\), библиотеки COFF \(.lib\), 32\-битовые файлы объектов OMF \(.obj\)|  
|Извлечение члена с помощью ключа \/EXTRACT|Библиотека COFF \(.lib\)|  
|Создание файла экспорта и библиотеки импорта с помощью ключа \/DEF|Файлы определения модуля \(.def\), файлы объектов COFF \(.obj\), библиотеки COFF \(.lib\), 32\-битовые файлы объектов OMF \(.obj\)|  
  
> [!NOTE]
>  Библиотеки OMF, созданные в 16\-битовой версии LIB, нельзя использовать в качестве входных файлов в 32\-битовой версии LIB.  
  
## См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)