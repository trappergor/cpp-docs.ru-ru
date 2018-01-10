---
title: "Ошибка компилятора C3492 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3492
dev_langs: C++
helpviewer_keywords: C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd8b70a22f24e41889c2c6d13cbb5fc2ff3e85e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3492"></a>Ошибка компилятора C3492
var: нельзя передавать член анонимного объединения  
  
 Вы не можете передавать член анонимного объединения  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Присвойте объединению имя и передайте полную структуру объединения в список передаваемых параметров лямбда-выражения.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3492, поскольку в нем передается член анонимного объединения:  
  
```  
// C3492a.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   };  
  
   ch = 'y';  
   [&x](char ch) { x = ch; }(ch); // C3492  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере устраняется ошибка C3492 путем предоставления объединению имени и передачи полной структуры объединения в список передаваемых параметров лямбда-выражения:  
  
```  
// C3492b.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   } u;  
  
   u.ch = 'y';  
   [&u](char ch) { u.x = ch; }(u.ch);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)