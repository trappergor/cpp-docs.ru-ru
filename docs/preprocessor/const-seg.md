---
title: const_seg
ms.date: 09/17/2018
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: c58f154f5e1ab6906b45d59f454a7dc2b5c0bfbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366593"
---
# <a name="constseg"></a>const_seg
Определяет сегмент, в котором [const](../cpp/const-cpp.md) переменные сохраняются в OBJ-файле.

## <a name="syntax"></a>Синтаксис

```
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Параметры

**push**<br/>
(Необязательно) Помещает запись во внутреннем стеке компилятора. Объект **принудительной** может иметь *идентификатор* и *имя сегмента*.

**pop**<br/>
(Необязательно) Удаление записи из верхней части внутреннего стека компилятора.

*identifier*<br/>
(Необязательно) При использовании с **принудительной**, назначает имя записи во внутреннем стеке компилятора. При использовании с **pop**, извлекает записи из внутреннего стека до *идентификатор* удаляется; Если *идентификатор* не найден во внутреннем стеке не выводятся.

С помощью *идентификатор* включает несколько записей, извлекаемых с помощью одного **pop** команды.

"*имя сегмента*"<br/>
(Необязательно) Имя сегмента. При использовании с **pop**, стек выводится и *имя сегмента* становится активным именем сегмента.

"*класс сегмента*"<br/>
(Необязательно) Включено для совместимости с C++ до версии 2.0. Игнорируется.

## <a name="remarks"></a>Примечания

Значение условия *сегмент* и *разделе* являются взаимозаменяемыми в этом разделе.

OBJ-файлы можно просмотреть при помощи [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию для хранения переменных `const` в OBJ-файле используется сегмент .rdata. Некоторые переменные `const`, например скаляры, автоматически подставляются в поток кода. Подставляемый код не отображается в сегменте .rdata.

Определение объекта, требующее динамической инициализации в `const_seg`, приводит к неопределенному поведению.

`#pragma const_seg` без параметров сбрасывает сегмент до .rdata.

## <a name="example"></a>Пример

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="comments"></a>Комментарии

См. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.

Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и функции ([code_seg](../preprocessor/code-seg.md)).

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)