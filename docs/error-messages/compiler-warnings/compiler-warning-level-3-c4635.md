---
title: "Предупреждение (уровень 3) C4635 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d4c85ca32903e20ea18a731872c25ee999b67f89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4635"></a>Предупреждение компилятора (уровень 3) C4635
Цель комментария XML-документа: неправильно сформированный XML: причина  
  
 Компилятор обнаружил проблему с XML-тегами.  Устраните проблему и выполните повторную компиляцию.  
  
 Следующий пример приводит к возникновению ошибки C4635:  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 Обратите внимание, что в результате для данного примера говорится: **Закрывающий тег member не соответствует открывающему тегу summary.**  
  
 Проблема в этом примере это закрывающий тег для \<Сводка настроек сформирован неправильно, и компилятор не распознает его как \<Сводка настроек закрывающего тега.  \<Элемента настроек тег включается в XDC-файл компилятором в каждой компиляции/doc.  Таким образом, проблема здесь в том, что закрывающий тег \</member настроек, не соответствует предыдущему открывающему тегу, обработанному компилятором (\<Сводка настроек.
