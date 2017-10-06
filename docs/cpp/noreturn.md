---
title: "noreturn | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 45de52c2c3c0b60a62bf19e38854c53e841ed500
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Атрибут `__declspec` сообщает компилятору, что функция не возвращается. Как следствие, компилятор знает, что код после вызова **__declspec(noreturn)** функция недоступен.  
  
 Если компилятор обнаруживает функцию с путем элемента управления, которая не возвращает значение, он создает предупреждение (C4715) или сообщение об ошибке (C2202). Если путь управления недостижим из-за функции, которая никогда не возвращает, можно использовать **__declspec(noreturn)** Чтобы избежать предупреждения или ошибки.  
  
> [!NOTE]
>  Добавление **__declspec(noreturn)** функции, которая возвращает может привести к неопределенному поведению.  
  
## <a name="example"></a>Пример  
 В следующем примере **else** предложение не содержит оператор return.  Объявление `fatal` как **__declspec(noreturn)** позволяет избежать ошибку или предупреждение.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
