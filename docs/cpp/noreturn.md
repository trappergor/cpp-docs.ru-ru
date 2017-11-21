---
title: "noreturn | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noreturn_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 91c6a7b38653a3bb0a86927ced602fd85ff29277
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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