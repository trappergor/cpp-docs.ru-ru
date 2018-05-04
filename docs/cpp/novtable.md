---
title: novtable | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 283ff09c320b67686e353f0497c665828cd8b5d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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