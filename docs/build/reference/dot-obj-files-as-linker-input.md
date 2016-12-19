---
title: "OBJ-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "OBJ-файлы в качестве входных файлов компоновщика"
  - "COFF-файлы"
  - "LINK - средство [C++], .OBJ-файлы"
  - "компоновщик [C++], OBJ-файлы в качестве входных"
  - "OBJ-файлы в качестве входных файлов компоновщика"
  - "файлы объектов, компоновщик - выходные данные"
  - "OMF-файлы объектов"
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# OBJ-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Средство компоновки \(LINK.EXE\) принимает OBJ\-файлы в формате COFF.  
  
## Заметки  
 Майкрософт предоставляет для загрузки документ, определяющий формат COFF.  Дополнительные сведения, загрузки версии 8.1 или более поздней версии [Исполняемый файл Microsoft переносимые и спецификация формата COFF](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## Поддержка Юникода  
 Начиная с Visual Studio 2005 компилятор Microsoft Visual C\+\+ распознает символы Юникод в идентификаторах в соответствии со стандартами ISO\/IEC C и С\+\+.  Предыдущие версии компилятора распознавали в идентификаторах только символы ASCII.  Поддержка Юникода в именах функций, классов и статических объектов возможна благодаря тому, что компилятор и компоновщик используют для символов COFF в OBJ\-файлах кодировку Юникод UTF\-8.  Обеспечена восходящая совместимость кодировки UTF\-8 с кодировкой ASCII, используемой в более ранних версиях Visual Studio.  
  
 Дополнительные сведения о компиляторе и компоновщике см. в разделе [Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md).  Дополнительные сведения о стандарта организации см. в разделе [Юникод](http://go.microsoft.com/fwlink/?LinkId=37123).  
  
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Поддержка Юникода](../../text/support-for-unicode.md)   
 [Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Стандарт юникод](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Спецификация формата COFF](http://go.microsoft.com/fwlink/?LinkId=93292)