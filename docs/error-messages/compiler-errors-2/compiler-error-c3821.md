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
ms.workload: cplusplus
ms.openlocfilehash: eda98ddd6247a2b3d137c015e5e4e3b06f04d821
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
