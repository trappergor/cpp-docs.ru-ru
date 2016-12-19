---
title: "Параметр /RANGE | Microsoft Docs"
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
  - "/RANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RANGE - параметр программы dumpbin"
  - "-RANGE - параметр (программа dumpbin)"
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметр /RANGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет параметры программы dumpbin при совместном использовании с другими ее параметрами, например \/RAWDATA или \/DISASM.  
  
## Синтаксис  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## Флаги  
 **vaMin**  
 Виртуальный адрес, с которого начинается операция dumpbin.  
  
 **vaMax** \(необязательно\)  
 Виртуальный адрес, на котором завершается операция dumpbin.  Если этот параметр не задан, операция dumpbin выполняется до конца файла.  
  
## Заметки  
 Чтобы просмотреть виртуальные адреса образа, используйте файл отображения образа \(относительный виртуальный адрес \+ базовый адрес\), параметр **\/DISASM** или **\/HEADERS** программы dumpbin, или окно дизассемблирования отладчика Visual Studio.  
  
## Пример  
 В этом примере параметр **\/range** используется для изменения параметров отображения параметра **\/disasm**.  В этом примере начальное значение представлено в форме десятичного, а конечное — в форме шестнадцатеричного числа.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)