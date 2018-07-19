---
title: Ошибка компилятора C2597 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45cf9054736117526ee5e79c0bafdd8fdee7c2e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229354"
---
# <a name="compiler-error-c2597"></a>Ошибка компилятора C2597
недопустимая ссылка на нестатический член identifier  
  
 Возможные причины:  
  
1.  Нестатический член используется в статической функции-члене. Для доступа к нестатическому члену необходимо передать или создать локальный экземпляр класса и использовать оператор доступа к члену (`.` или `->`).  
  
2.  Указанный идентификатор не является членом класса, структуры или объединения. Проверьте написание идентификатора.  
  
3.  Оператор доступа к члену ссылается на функцию, не являющуюся членом.  
  
4.  В следующем примере показано возникновение ошибки C2597 и приводятся сведения по ее устранению.  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
```