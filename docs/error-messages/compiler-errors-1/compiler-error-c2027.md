---
title: Ошибка компилятора C2027 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be3c85d2ffbd3fffe4e1e6ce6dafc615f199c00a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167448"
---
# <a name="compiler-error-c2027"></a>Ошибка компилятора C2027
Использование неопределенного типа «тип»  
  
 Тип не может использоваться, пока оно определено. Чтобы устранить эту ошибку, убедитесь, что перед обращением полностью определен тип.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2027.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## <a name="example"></a>Пример  
 Можно объявить указатель на объявленный, но неопределенный тип.  Однако Visual C++ не допускаются ссылки на неопределенный тип.  
  
 Следующий пример приводит к возникновению ошибки C2027.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```