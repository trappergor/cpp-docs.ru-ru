---
title: Ошибка компилятора C2912 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2912
dev_langs:
- C++
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b165e868f4a2055d692d768c7e5c0164dd34002
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241227"
---
# <a name="compiler-error-c2912"></a>Ошибка компилятора C2912
явная специализация; declaration не является специализацией функции-шаблона  
  
 Невозможно специализировать нешаблонную функцию.  
  
 Следующий пример приводит к возникновению ошибки C2912:  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003: для каждой явной специализации необходимо выбрать параметры явной специализации так, чтобы они соответствовали параметрам первичного шаблона.  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```