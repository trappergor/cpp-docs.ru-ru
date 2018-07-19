---
title: Ошибка компилятора C2140 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2140
dev_langs:
- C++
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1634e2a61ed9ee22bdfde619f8710226b74e48a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169690"
---
# <a name="compiler-error-c2140"></a>Ошибка компилятора C2140
«Тип»: тип, зависящий от параметра универсального типа не допускается в качестве аргумента в характеристике внутреннего типа компилятора «Признак»  
  
 Недопустимый спецификатор типа передан признака типа.  
  
 Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2140.  
  
```  
// C2140.cpp  
// compile with: /clr /c  
template <class T>  
  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class x {};  
  
generic <class T>  
ref class C {  
   void f() {  
      System::Console::WriteLine(__is_polymorphic(T));   // C2140  
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140  
  
      System::Console::WriteLine(__is_polymorphic(x));   // OK  
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK  
   }  
};  
```