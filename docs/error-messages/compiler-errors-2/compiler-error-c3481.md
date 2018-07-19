---
title: Ошибка компилятора C3481 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77fc0f542a74cb077e59882e31dd1acb10c7b7e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250489"
---
# <a name="compiler-error-c3481"></a>Ошибка компилятора C3481
var: переменная, передаваемая в лямбда-выражение, не найдена  
  
 Компилятору не удалось найти определение переменной, которая передается в список передаваемых параметров в лямбда-выражении.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите переменную из списка передаваемых параметров в лямбда-выражении.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3481, так как переменная `n` не определена:  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)