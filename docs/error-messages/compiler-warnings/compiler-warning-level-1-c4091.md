---
title: Предупреждение компилятора (уровень 1) предупреждение C4091 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4091
dev_langs:
- C++
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79a0a74ad2cf6471679fd776f296d465ee8dd29c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276520"
---
# <a name="compiler-warning-level-1-c4091"></a>Предупреждение компилятора (уровень 1) предупреждение C4091
«Ключевое слово»: игнорируется слева от «тип», когда переменная не объявлена  
  
 Компилятор обнаружил ситуацию, когда пользователь, вероятно, предназначен для объявления переменной, но компилятор не может объявить переменную.  
  
## <a name="example"></a>Пример  
 Объект `__declspec` атрибут в начале объявления пользовательского типа относится к переменной этого типа. C4091 указывает, что переменная не объявлена. Следующий пример приводит к возникновению ошибки C4091.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>Пример  
 Если идентификатор объявлен как typedef, он также не может быть имя переменной. Следующий пример приводит к возникновению ошибки C4091.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```