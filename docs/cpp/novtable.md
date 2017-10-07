---
title: "novtable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 7064bd08a97f3eabbf337b1a351614e94d6458dd
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Представляет собой расширенный атрибут `__declspec`.  
  
 Эта форма ключевого слова `__declspec` применима к любым объявлениям классов, но ее следует применять только к чистым классам интерфейсов, т. е к классам, для которых никогда не будут создаваться собственные экземпляры. `__declspec` не позволяет компилятору создавать код для инициализации vfptr в конструкторах и деструкторе класса. Во многих случаях это приводит к удалению единственной ссылки на связанную с классом таблицу vtable, в результате чего компоновщик удаляет ее. Использование такой формы `__declspec` может приводить к значительному сокращению размера кода.  
  
 Если попытаться создать экземпляр класса, помеченного атрибутом `novtable`, а затем обратиться к члену класса, возникает нарушение прав доступа (AV).  
  
## <a name="example"></a>Пример  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
```Output  
In Y  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
