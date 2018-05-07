---
title: Предупреждение (уровень 3) C4635 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dcc4b7466ed53a187b7f34ec45084a94adb59b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
  
 Проблема в этом примере это закрывающий тег для \<сводки > сформирован неправильно, и компилятор не распознает его как \<сводки > закрывающего тега.  \<Член > тег включается в XDC-файл компилятором в каждой компиляции/doc.  Таким образом, проблема здесь в том, что закрывающий тег \</member >, не соответствует предыдущему открывающему тегу, обработанному компилятором (\<сводки >.