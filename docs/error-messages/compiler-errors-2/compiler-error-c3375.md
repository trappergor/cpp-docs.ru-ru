---
title: Ошибка компилятора C3375 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3375
dev_langs:
- C++
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11805b7ef714c65ff9816828aeea10baa2217ff6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256474"
---
# <a name="compiler-error-c3375"></a>Ошибка компилятора C3375
"функция": неоднозначная функция делегата  
  
 Создание экземпляра делегата могло быть выполнено в статической функции-члене или как непривязанного делегата для функции экземпляра, поэтому компилятор выдал данную ошибку.  
  
 Дополнительные сведения см. в разделе [delegate (расширения компонентов C++)](../../windows/delegate-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3375:  
  
```  
// C3375.cpp  
// compile with: /clr  
ref struct R {  
   static void f(R^) {}  
   void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::f);   // C3375  
}  
```