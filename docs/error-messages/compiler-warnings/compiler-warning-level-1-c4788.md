---
title: "Предупреждение компилятора (уровень 1) C4788 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4788"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4788"
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4788
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": идентификатор был сокращен до "число" знаков  
  
 Компилятор ограничивает максимальную длину, разрешенную для имени функции.  Когда компилятор создает фанклеты для кода EH\/SEH, он формирует имя фанклета, добавляя к имени функции некоторый текст, например "\_\_catch", "\_\_unwind" или другую строку.  
  
 Итоговое имя фанклета может быть очень длинным, и компилятор сокращает его и создает предупреждение C4788.  
  
 Чтобы решить эту проблему, сократите начальное имя функции.  Если функция является методом или функцией шаблона C\+\+, используйте определение типа для части имени.  Примеры.  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 можно заменить на:  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Это предупреждение возникает только в компиляторе [!INCLUDE[vcprx64](../Token/vcprx64_md.md)].