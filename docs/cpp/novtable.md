---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: ccf544608bcba83af17702767562ef93d775b5a9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227261"
---
# <a name="novtable"></a>novtable

**Блок, относящийся только к системам Microsoft**

Это **`__declspec`** Расширенный атрибут.

Такая форма применима **`__declspec`** к любому объявлению класса, но должна применяться только к чистым классам интерфейса, то есть к классам, экземпляры которых никогда не будут создаваться самостоятельно. **`__declspec`** Компонент останавливает компилятор на создание кода для инициализации вфптр в конструкторах и деструкторе класса. Во многих случаях это приводит к удалению единственной ссылки на связанную с классом таблицу vtable, в результате чего компоновщик удаляет ее. Использование такой формы **`__declspec`** может привести к значительному сокращению размера кода.

Если попытаться создать экземпляр класса, помеченного как, **`novtable`** а затем получить доступ к члену класса, вы получите нарушение прав доступа (AV).

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

[`__declspec`](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
