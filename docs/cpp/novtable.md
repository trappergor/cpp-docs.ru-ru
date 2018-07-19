---
title: novtable | Документация Майкрософт
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
ms.openlocfilehash: 3ad0c50330d174a6139ce6e588b278e03cd99562
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944574"
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Это **__declspec** расширенный атрибут.  
  
 Такая форма **__declspec** могут применяться к любым объявлениям классов, но должно применяться только к чистым классам интерфейсов, то есть классы, которые никогда не будет создаваться сами по себе. **__Declspec** предотвращает компилятором код для инициализации vfptr в конструкторах и деструкторе класса. Во многих случаях это приводит к удалению единственной ссылки на связанную с классом таблицу vtable, в результате чего компоновщик удаляет ее. Использование такой формы **__declspec** может привести к значительному сокращению размера кода.  
  
 Если попытаться создать экземпляр класса, помеченного атрибутом `novtable`, а затем обратиться к члену класса, возникает нарушение прав доступа (AV).  
  
## <a name="example"></a>Пример  
  
```cpp 
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