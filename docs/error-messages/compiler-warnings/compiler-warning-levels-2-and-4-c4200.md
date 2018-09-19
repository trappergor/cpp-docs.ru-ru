---
title: Предупреждение компилятора (уровни 2 и 4) C4200 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4200
dev_langs:
- C++
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34e0befb93db742bb2d132b2092414a1a167b87b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100725"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Предупреждение компилятора (уровни 2 и 4) C4200

использовано нестандартное расширение: массив нулевого размера в конструкции/объединении

Указывает, что структура или объединение содержит массив нулевого размера.

Объявление массива нулевого размера — это расширение Майкрософт. При этом возникает предупреждение уровня 2 при компиляции файла C++ и предупреждение уровня 4 при компиляции файла C. При компиляции C++ также появляется предупреждение: «Невозможно создать конструктор копии или оператор присвоения копии, когда UDT содержит массив нулевого размера». Этот пример создает предупреждение C4200:

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

Это нестандартное расширение, часто используемое для реализации взаимодействия кода с существующими структурами данных переменной длины. Если этот сценарий применим для вашего кода, можно отключить это предупреждение:

## <a name="example"></a>Пример

```cpp
// C4200b.cpp
// compile by using: cl /W4 c4200a.cpp
#pragma warning(disable : 4200)
struct A {
    int a[0];
};
int main() {
}
```