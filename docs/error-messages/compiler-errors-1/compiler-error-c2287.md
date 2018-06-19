---
title: Ошибка компилятора C2287 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2287
dev_langs:
- C++
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b78dd6d7ffc44822cdff383f88b11a6cd899adf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170272"
---
# <a name="compiler-error-c2287"></a>Ошибка компилятора C2287
«класс»: представление наследования: «Представление1» более специализирован, чем требуется представление «2»  
  
 Класс объявлен с представлением проще, чем требуется.  
  
 Следующий пример приводит к возникновению ошибки C2287:  
  
```  
// C2287.cpp  
// compile with: /vmg /c  
class __single_inheritance X;  
class __single_inheritance Y;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2287  X uses multiple inheritance  
struct Y : A { };  // OK  
```