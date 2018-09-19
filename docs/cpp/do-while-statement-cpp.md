---
title: Оператор do-while (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37155be11caaee9c609a0e11ddbfeb5d62856903
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071202"
---
# <a name="do-while-statement-c"></a>Оператор do-while (C++)

Выполняет *statement* (инструкции) циклически, пока указанное условие завершения *expression* (выражение) не станет равно нулю.

## <a name="syntax"></a>Синтаксис

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Примечания

Тест условия завершения выполняется после каждого выполнения цикла; Таким образом **сделать-хотя** цикл выполняется один или несколько раз, в зависимости от значения выражения завершения. **Сделать-хотя** инструкции также прерывается, когда [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), или [возвращают](../cpp/return-statement-cpp.md) в теле оператора выполняется оператор.

Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:

1. Выполняется тело цикла.

1. Затем вычисляется значение *expression*. Если *выражение* имеет значение false, **сделать-хотя** завершается и управление передается следующему оператору программы. Если *expression* имеет значение true (то есть не равно нулю), процесс повторяется с шага 1.

## <a name="example"></a>Пример

В следующем образце показано **сделать-хотя** инструкции:

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>См. также

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор for (C++)](../cpp/for-statement-cpp.md)<br/>
[Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md)
