---
title: Ошибка компилятора C3485 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cd9de6f300fed673d588df60d7acca15b104b61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258138"
---
# <a name="compiler-error-c3485"></a>Ошибка компилятора C3485
определение лямбда-выражения не может содержать cv-квалификаторы  
  
 Нельзя использовать квалификатор `const` или `volatile` как часть определения лямбда-выражения.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите квалификатор `const` или `volatile` из определения лямбда-выражения.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример приводит к возникновению ошибки C3485, так как в нем квалификатор `const` используется как часть определения лямбда-выражения.  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)