---
title: Оператор for (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a845fde2010f17d4d92be0d8ed0d4cce0bdb070
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061506"
---
# <a name="for-statement-c"></a>Оператор for (C++)

Повторяет выполнение инструкций (statement), пока условие не станет ложным. Сведения об операторе for для диапазона см. в разделе [Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Синтаксис

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>Примечания

Используйте **для** инструкции для создания циклов, которые должны выполняться заданное число раз.

**Для** оператор состоит из трех необязательных частей, как показано в следующей таблице.

### <a name="for-loop-elements"></a>элементы цикла for

|Название части|Когда выполняется|Описание|
|-----------------|-------------------|-----------------|
|`init-expression`|Выражение `init-expression` выполняется только один раз перед любой другой частью инструкции **for**. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию. `statement` выполняется, только если `cond-expression` имеет значение true (не равное нулю).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу. Обычно используется для проверки критериев завершения цикла for.|
|`loop-expression`|В конце каждой итерации `statement`. После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|

Ниже приведены примеры различных способов использования **для** инструкции.

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
}
    // Output: 012
```

`init-expression` и `loop-expression` могут содержать несколько операторов, разделенных запятыми. Пример:

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

`loop-expression` можно увеличить или уменьшить, или изменить другими способами.

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

Объект **для** цикл завершается, когда [break](../cpp/break-statement-cpp.md), [возвращают](../cpp/return-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md) (оператору с меткой за пределами **для**цикла) в пределах `statement` выполняется. Объект [по-прежнему](../cpp/continue-statement-cpp.md) инструкции в **для** цикла завершает только текущую итерацию.

Если `cond-expression` — этот параметр опущен, его значение считается равным true и **для** цикл не завершится без **break**, **возвращают**, или **goto** в рамках `statement`.

Несмотря на то что эти три поля **для** инструкции обычно используются для инициализации, тестирования на завершение и увеличения, они не ограничиваются такими способами использования. Например, следующий код выводит числа от 0 до 4. В этом случае в `statement` будет пусто:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>циклы for и стандарт C++

Стандарт C++ указывает, что переменная, объявленная в **для** цикла должна выйти из области после **для** завершения цикла. Пример:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

По умолчанию в разделе [/Ze](../build/reference/za-ze-disable-language-extensions.md), переменной, объявленной в **для** цикл остается в пределах области до **для** цикл внешней области.

[/ Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) включает стандартное поведение переменных, объявленных в циклах for, без необходимости указания `/Za`.

Можно также использовать различия области видимости **для** цикл для повторного объявления переменных в `/Ze` следующим образом:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Это более точно имитирует стандартное поведение переменной, объявленной в **для** цикл, который требует переменные, объявленные в **для** цикл за пределы области видимости после выполнения цикла. Если переменная объявлена в **для** цикл, компилятор внутренним образом повышает ее локальной переменной в **для** цикл включающей области, даже если локальная переменная с тем же именем уже существует.

## <a name="see-also"></a>См. также

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md)
