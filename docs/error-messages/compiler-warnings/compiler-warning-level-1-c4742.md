---
title: Предупреждение компилятора (уровень 1) C4742 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4742
dev_langs:
- C++
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 622a1b1cd62024da58191ce1312c391dd39e0d28
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088596"
---
# <a name="compiler-warning-level-1-c4742"></a>Предупреждение компилятора (уровень 1) C4742

«var» имеет различное выравнивание в «файл1» и «файл2»: номер и номер

Внешняя переменная, которая была определена в двух файлах или ссылаться на имеет различное выравнивание в этих файлах. Это предупреждение создается в том случае, когда компилятор обнаруживает, что `__alignof` для переменной в *file1* отличается от `__alignof` для переменной в *"файл2"*. Это может быть вызвано использование несовместимых типов при объявлении переменной в разных файлах, или с помощью непарный `#pragma pack` в разных файлах.

Чтобы устранить это предупреждение, используйте одно и то же определение типа или использовать разные имена для переменных.

Дополнительные сведения см. в разделе [пакет](../../preprocessor/pack.md) и [оператор __alignof](../../cpp/alignof-operator.md).

## <a name="example"></a>Пример

Это первый файл, который определяет тип.

```
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4742.

```
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```