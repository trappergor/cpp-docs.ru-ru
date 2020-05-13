---
title: Оператор for (C++)
description: Ссылка на стандартную си-за выписки в Microsoft Visual Studio C .
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 92f7ae4b1f2fbaaf710cd5a8739b78cb98a0accb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375380"
---
# <a name="for-statement-c"></a>Оператор for (C++)

Выполняет оператор повторно до тех пор, пока условное значение не станет false. Для получения информации о диапазоне, основанном на выписке, [см.](../cpp/range-based-for-statement-cpp.md)

## <a name="syntax"></a>Синтаксис

> **`for (`***инит-выражение* **`;`** *конд-выражение* **`;`** *петли-выражение***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_Заявление_**`;`**

## <a name="remarks"></a>Remarks

Используйте **для** оператора для построения циклов, которые должны выполняться определенное количество раз.

**Для** заявления состоит из трех факультативных частей, как показано в следующей таблице.

### <a name="for-loop-elements"></a>элементы цикла for

|Имя синтаксиса|Когда выполняется|Описание|
|-----------------|-------------------|-----------------|
|`init-expression`|Перед любым другим **for** элементом `init-expression` оператора выполняется только один раз. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию. `statement` выполняется, только если `cond-expression` имеет значение true (не равное нулю).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу. Обычно используется для проверки критериев завершения цикла for.|
|`loop-expression`|В конце каждой итерации `statement`. После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|

Следующие примеры показывают различные способы использования **оператора.**

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

A **для** цикла завершается, когда [выполняется перерыв,](../cpp/break-statement-cpp.md) [возврат](../cpp/return-statement-cpp.md)или [goto](../cpp/goto-statement-cpp.md) (к помеченной выписке за **пределами** цикла) внутри. `statement` [Продолжение](../cpp/continue-statement-cpp.md) оператора в **цикле** завершает только текущую итерацию.

Если `cond-expression` опущен, `true`он считается, и **для** цикла не будет прекращаться без **перерыва,** **возвращения,** или **goto** внутри `statement`.

Хотя три поля **оператора** обычно используются для инициализации, тестирования на прекращение и приращения, они не ограничиваются этими использованиями. Например, следующий код выводит числа от 0 до 4. В данном случае `statement` является оператором null:

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

Стандарт СЗЗ гласит, что переменная, заявленная в **цикле,** должна выйти за рамки после окончания **цикла.** Пример:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

По умолчанию, под [/Зе](../build/reference/za-ze-disable-language-extensions.md), переменная, объявленная в **для** цикла остается в области до тех пор, пока **для** цикла прилагая область заканчивается.

[/C:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) позволяет стандартное поведение переменных, заявленных для `/Za`циклов без необходимости указывать.

Также можно использовать различия в прослеживаниях **для** цикла для `/Ze` повторного объявления переменных следующим образом:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Это поведение более точно имитирует стандартное **for** поведение переменной, объявленной в цикле, которая требует, чтобы переменные, заявленные в **цикле,** выходили из сферы действия после выполнения цикла. Когда переменная заявлена **for** в цикле, компилятор внутренне продвигает ее к локальной переменной в прилагаемом области **цикла.** Это способствует, даже если есть уже локальная переменная с тем же именем.

## <a name="see-also"></a>См. также раздел

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[в то время как Заявление (СЗ)](../cpp/while-statement-cpp.md)<br/>
[делать-в то время как Заявление (СЗ)](../cpp/do-while-statement-cpp.md)<br/>
[Основанное на диапазоне выражение for (C++)](../cpp/range-based-for-statement-cpp.md)
