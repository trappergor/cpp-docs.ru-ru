---
title: Предупреждение компилятора (уровень 1) C4305 | Документация Майкрософт
ms.custom: ''
ms.date: 1/17/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88ae0fb38b7e6af14525906e90486a68ce22ee56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086828"
---
# <a name="compiler-warning-level-1-c4305"></a>Предупреждение компилятора (уровень 1) C4305

> "*контекст*": усечение из "*тип1*«to»*тип2*"

## <a name="remarks"></a>Примечания

Это предупреждение выдается в том случае, когда значение преобразуется в тип меньшего размера в инициализации или в качестве аргумента конструктора, что приводит к потере данных.

## <a name="example"></a>Пример

Этот пример показывает два способа, может появиться это предупреждение:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Чтобы устранить эту проблему, инициализировать с помощью значения правильного типа, или использовать явное приведение к правильному типу. Например, использовать **число с плавающей запятой** литерал, например 2.71828f вместо **двойные** (тип по умолчанию литералы с плавающей запятой) для инициализации **число с плавающей запятой** переменной, или для передачи конструктор, принимающий **float** аргумент.
