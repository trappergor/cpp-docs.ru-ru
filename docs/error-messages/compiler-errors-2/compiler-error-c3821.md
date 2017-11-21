---
title: "Ошибка компилятора C3821 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3821
dev_langs: C++
helpviewer_keywords: C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 47e0a2ed3c824ed1598f7e998d4966b95cc9233b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3821"></a>Ошибка компилятора C3821
«функция»: управляемый тип или функция не может использоваться в неуправляемую функцию  
  
 Функции со встроенной сборкой или [setjmp](../../c-runtime-library/reference/setjmp.md) не может содержать типы значений или управляемые классы. Чтобы устранить эту ошибку, удалите встроенной сборке и `setjmp` или удалите управляемые объекты.  
  
 C3821 также может возникать при попытке использования автоматического хранения в функции с переменным количеством аргументов.  Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) и [семантика стека C++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3821.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3821.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
