---
title: Ошибка компилятора C2191 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa4b590b494355450909032c78822553004beddc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2191"></a>Ошибка компилятора C2191
второй список параметров длиннее первого  
  
 Функция C была объявлена во второй раз с более длинным списком параметров. C не поддерживает перегруженные функции.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2191:  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```