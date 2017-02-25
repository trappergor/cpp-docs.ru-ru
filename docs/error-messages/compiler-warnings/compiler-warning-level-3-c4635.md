---
title: "Предупреждение компилятора (уровень 3) C4635 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4635"
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 3) C4635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Цель комментария XML\-документа: неправильно сформированный XML: причина  
  
 Компилятор обнаружил проблему с XML\-тегами.  Устраните проблему и выполните повторную компиляцию.  
  
 Следующий пример приводит к возникновению ошибки C4635:  
  
```  
// C4635.cpp // compile with: /doc /clr /W3 /c /// <summary> /// The contents of the folder have changed. /// <summary/>   // C4635 // try the following line instead // /// </summary> public ref class Test {};  
```  
  
 Обратите внимание, что в результате для данного примера говорится: **Закрывающий тег member не соответствует открывающему тегу summary.**  
  
 Проблема в этом примере заключается в том, что закрывающий тег для \<summary\> сформирован неправильно, и компилятор не распознает его как закрывающий тег \<summary\>.  Тег \<member\> включается в XDC\-файл компилятором в каждой компиляции \/doc.  Таким образом, проблема здесь в том, что закрывающий тег \<\/member\> не соответствует предыдущему открывающему тегу, обработанному компилятором \(\<summary\>\).