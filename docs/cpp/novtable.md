---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 9dcca6ec07a19d53da238020805299b652cbf919
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630247"
---
# <a name="novtable"></a>novtable

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Это **__declspec** расширенный атрибут.

Такая форма **__declspec** могут применяться к любым объявлениям классов, но должно применяться только к чистым классам интерфейсов, то есть классы, которые никогда не будет создаваться сами по себе. **__Declspec** предотвращает компилятором код для инициализации vfptr в конструкторах и деструкторе класса. Во многих случаях это приводит к удалению единственной ссылки на связанную с классом таблицу vtable, в результате чего компоновщик удаляет ее. Использование такой формы **__declspec** может привести к значительному сокращению размера кода.

Если попытаться создать экземпляр класса, помеченного **novtable** и затем получить доступ к члену класса, вы получите нарушение прав доступа (AV).

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

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)