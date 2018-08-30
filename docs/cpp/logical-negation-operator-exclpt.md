---
title: 'Оператор логического отрицания: ! | Документы Майкрософт'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4594a8b1a881b6fa92909e7c7014087ff6240de8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211822"
---
# <a name="logical-negation-operator-"></a>Оператор логического отрицания: !

## <a name="syntax"></a>Синтаксис

```
! cast-expression
```

## <a name="remarks"></a>Примечания

Оператор логического отрицания (**!**) меняет значение своего операнда. Операнд должен иметь арифметический тип или тип указателя (либо выражение, результатом которого является арифметический тип или тип указателя). Операнд неявно преобразуется в тип **bool**. Результат имеет значение TRUE, если преобразованный операнд — FALSE. Результатом является значение FALSE, если преобразованный операнд имеет значение TRUE. Результат имеет тип **bool**.

Для выражения *e*, унарное выражение `!e` эквивалентно выражению `(e == 0)`, за исключением случаев, когда используются перегруженные операторы.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для !

**Не** оператор является вариант написания из **!**. Существует два способа для доступа к **не** оператор в программах: включить файл заголовка \<iso646.h >, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)<br/>
