---
title: Оператор for (C++)
description: Ссылка на стандартный оператор C++ for в Microsoft Visual Studio C++.
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 16486fd58a9b3fec750ebef6ec6647f9d92bca3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231186"
---
# <a name="for-statement-c"></a>Оператор for (C++)

Выполняет оператор повторно до тех пор, пока условное значение не станет false. Сведения об операторе for на основе диапазона см. в разделе [оператор на основе диапазона for (C++)](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Синтаксис

> **`for (`***init-Expression* **`;`** *cond-Expression* **`;`** *выражение цикла***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_баланс_**`;`**

## <a name="remarks"></a>Remarks

Используйте **`for`** инструкцию для создания циклов, которые должны выполняться указанное число раз.

**`for`** Инструкция состоит из трех дополнительных частей, как показано в следующей таблице.

### <a name="for-loop-elements"></a>элементы цикла for

|Имя синтаксиса|Когда выполняется|Описание:|
|-----------------|-------------------|-----------------|
|`init-expression`|Перед любым другим элементом инструкции выполняется **`for`** `init-expression` только один раз. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию. `statement` выполняется, только если `cond-expression` имеет значение true (не равное нулю).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу. Обычно используется для проверки критериев завершения цикла for.|
|`loop-expression`|В конце каждой итерации `statement`. После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|

В следующих примерах показаны различные способы использования **`for`** инструкции.

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

`init-expression` и `loop-expression` могут содержать несколько операторов, разделенных запятыми. Например:

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

**`for`** Цикл завершается, когда выполняется [прерывание](../cpp/break-statement-cpp.md), [Возврат](../cpp/return-statement-cpp.md)или [Переход](../cpp/goto-statement-cpp.md) (к оператору с меткой вне **`for`** цикла) внутри `statement` . Оператор [Continue](../cpp/continue-statement-cpp.md) в **`for`** цикле завершает только текущую итерацию.

Если `cond-expression` аргумент опущен, то считается, что **`true`** **`for`** цикл не завершается без оператора **`break`** , **`return`** или **`goto`** в `statement` .

Хотя три поля **`for`** инструкции обычно используются для инициализации, тестирования завершения и увеличения, они не ограничиваются этими применениями. Например, следующий код выводит числа от 0 до 4. В данном случае `statement` является оператором null:

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

Стандарт C++ говорит о том, что переменная, объявленная в **`for`** цикле, должна выйти из области действия после **`for`** завершения цикла. Например:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

По умолчанию в параметре [/Ze](../build/reference/za-ze-disable-language-extensions.md)переменная, объявленная в **`for`** цикле, остается в области видимости до **`for`** конца охватывающей области цикла.

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) обеспечивает стандартное поведение переменных, объявленных в цикле for, без необходимости указывать `/Za` .

Можно также использовать различия в области **`for`** действия цикла для повторного объявления переменных в `/Ze` следующим образом:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Такое поведение более точно имитирует стандартное поведение переменной, объявленной в **`for`** цикле, что требует, чтобы переменные, объявленные в **`for`** цикле, выходят за пределы области действия после завершения цикла. При объявлении переменной в **`for`** цикле компилятор внутренне переводит его в локальную переменную в **`for`** области видимости цикла. Она повышается, даже если уже существует локальная переменная с таким же именем.

## <a name="see-also"></a>См. также статью

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Основанное на диапазоне выражение for (C++)](../cpp/range-based-for-statement-cpp.md)
