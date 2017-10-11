---
title: "Ошибка компилятора C3539 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 03283217be6aabbf216e2e60ad47abfc01a961d6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3539"></a>Ошибка компилятора C3539
«Тип»: аргумент шаблона не может быть типом, содержащим «auto»  
  
 Указанный тип аргумента шаблона не может содержать `auto` ключевое слово.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не указывайте аргумент шаблона с `auto` ключевое слово.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)
