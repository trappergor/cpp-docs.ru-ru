---
title: Ошибка компилятора C2990 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669cfcd1e9a715b247c9264856e8877275d6407c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2990"></a>Ошибка компилятора C2990
«класс»: тип, не являющийся классом уже объявлен как тип класса  
  
 Переопределяет универсальный или шаблонный класс, не являющийся универсальным или класса-шаблона. Проверьте файлы заголовков на наличие конфликтов.  
  
 Следующий пример приводит к возникновению ошибки C2990:  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 Ошибка C2990 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 Ошибка C2990 также может возникать из-за критических изменений в компиляторе Visual C++ для Visual C++ 2005; Компилятор теперь требует нескольких объявлениях того же типа идентичности в отношении спецификации шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2990:  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```