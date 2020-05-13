---
title: Предупреждение компилятора (уровень 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 1c4a7ca806430c73c8e8396e596782253cc06f09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162742"
---
# <a name="compiler-warning-level-1-c4383"></a>Предупреждение компилятора (уровень 1) C4383

"instance_dereference_operator": значение разыменования маркера может измениться, если определен определенный пользователем оператор "operator"; Напишите оператор как статическую функцию, чтобы она была явной относительно операнда

При добавлении определяемого пользователем переопределения экземпляра оператора разыменования в управляемом типе можно переопределить способность оператора разыменования типа возвращать объект обработчика. Попробуйте написать статический, определяемый пользователем оператор разыменования.

Дополнительные сведения см. в разделе Оператор [Handle to Object (^)](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) и [Отслеживаемый оператор Reference](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

Кроме того, оператор экземпляра недоступен для компиляторов других языков через метаданные, на которые имеются ссылки. Дополнительные сведения см. в разделе [определяемые пользователем операторыC++(/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4383.

```cpp
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```
