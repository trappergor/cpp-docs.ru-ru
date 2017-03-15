---
title: "Неустранимая ошибка C1900 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1900"
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Несоответствие между "tool1" версии "number1" и "tool2" версии "number2"  
  
 Средства, запускаемые на разных этапах работы компилятора, не совпадают.  ***number1*** и ***number2*** обозначают даты файлов.  Например, на первом проходе внешний сегмент компилятора запускает \(c1.dll\), а на втором проходе внутренний сегмент компилятора запускает \(c2.dll\).  Даты файлов должны совпадать.  
  
 Чтобы устранить эту проблему, убедитесь, что к Visual Studio применены все обновления.  Если проблема сохранится, используйте элемент панели управления **Программы и компоненты** для восстановления или переустановки Visual Studio.