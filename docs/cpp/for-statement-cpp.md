---
title: Оператор for (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: e3dfdb45bdf8a508eca9d29e90b3f7c05e7b147d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179918"
---
# <a name="for-statement-c"></a>Оператор for (C++)

Выполняет оператор повторно до тех пор, пока условное значение не станет false. Дополнительные сведения об операторе for на основе диапазона см. в разделе [оператор на основе диапазонаC++for ()](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Синтаксис

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>Remarks

Используйте оператор **for** для создания циклов, которые должны выполняться указанное число раз.

Оператор **for** состоит из трех дополнительных частей, как показано в следующей таблице.

### <a name="for-loop-elements"></a>элементы цикла for

|Имя синтаксиса|Когда выполняется|Description|
|-----------------|-------------------|-----------------|
|`init-expression`|Перед любым другим элементом оператора **for** `init-expression` выполняется только один раз. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию. `statement` выполняется, только если `cond-expression` имеет значение true (не равное нулю).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу. Обычно используется для проверки критериев завершения цикла for.|
|`loop-expression`|В конце каждой итерации `statement`. После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|

В следующих примерах показаны различные способы использования инструкции **for** .

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

Цикл **for** завершается, когда выполняется [прерывание](../cpp/break-statement-cpp.md), [Возврат](../cpp/return-statement-cpp.md)или [Переход](../cpp/goto-statement-cpp.md) (к оператору с меткой вне цикла **for** ) в `statement`. Оператор [Continue](../cpp/continue-statement-cpp.md) в цикле **for** завершает только текущую итерацию.

Если аргумент `cond-expression` опущен, он считается истинным, а цикл **for** не завершится без **прерывания**, **возврата**или перехода **в пределах `statement`** .

Хотя три поля оператора **for** обычно используются для инициализации, тестирования завершения и увеличения, они не ограничиваются этими применениями. Например, следующий код выводит числа от 0 до 4. В данном случае `statement` является оператором null:

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

C++ Стандарт говорит о том, что переменная, объявленная в цикле **for** , должна выйти из области действия после завершения цикла **for** . Пример:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

По умолчанию в параметре [/Ze](../build/reference/za-ze-disable-language-extensions.md)переменная, объявленная в цикле **for** , остается в области до конца охватывающей области цикла **for** .

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) обеспечивает стандартное поведение переменных, объявленных в цикле for, без необходимости указания `/Za`.

Также можно использовать различия в области действия цикла **for** для повторного объявления переменных в `/Ze` следующим образом:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Это более точно имитирует стандартное поведение переменной, объявленной в цикле **for** , что требует, чтобы переменные, объявленные в цикле **for** , выходят за пределы области действия после завершения цикла. При объявлении переменной в цикле **for** компилятор внутренне переводит его в локальную переменную в области видимости цикла **for** , даже если уже существует локальная переменная с таким же именем.

## <a name="see-also"></a>См. также раздел

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
