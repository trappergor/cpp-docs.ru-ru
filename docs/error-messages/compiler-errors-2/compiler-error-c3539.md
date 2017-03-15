---
title: "Ошибка компилятора C3539 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f7e9f8d260d17d7561077aabb0dfc26bf20f8c07
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3539"></a>Ошибка компилятора C3539
«Тип»: аргумент шаблона не может быть тип, который содержит «auto»  
  
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
 [Ключевое слово Auto](../../cpp/auto-keyword.md)
