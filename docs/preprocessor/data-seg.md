---
title: data_seg
ms.date: 10/22/2018
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: 414fc542aa3f84f985e326960d8cf73b67fd1580
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456385"
---
# <a name="dataseg"></a>data_seg

Задает сегмент данных, в котором инициализированные переменные сохраняются в OBJ-файле.

## <a name="syntax"></a>Синтаксис

```
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Параметры

**push**<br/>
(Необязательно) Помещает запись во внутреннем стеке компилятора. Объект **принудительной** может иметь *идентификатор* и *имя сегмента*.

**pop**<br/>
(Необязательно) Удаление записи из верхней части внутреннего стека компилятора.

*identifier*<br/>
(Необязательно) При использовании с **принудительной**, назначает имя записи во внутреннем стеке компилятора. При использовании с **pop**, извлекает записи из внутреннего стека до *идентификатор* удаляется; Если *идентификатор* не найден во внутреннем стеке не выводятся.

*Идентификатор* включает несколько записей, извлекаемых с помощью одного **pop** команды.

*«Имя сегмента»*<br/>
(Необязательно) Имя сегмента. При использовании с **pop**, стек выводится и *имя сегмента* становится активным именем сегмента.

*«Сегмент class»*<br/>
(Необязательно) Включено для совместимости с C++ до версии 2.0. Игнорируется.

## <a name="remarks"></a>Примечания

Значение условия *сегмент* и *разделе* являются взаимозаменяемыми в этом разделе.

OBJ-файлы можно просмотреть при помощи [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию сегмент в OBJ-файле для инициализированных переменных — DATA. Неинициализированные переменные считаются инициализированными с нулем и сохраняются в BSS-файле.

**data_seg** без параметров сбрасывает сегмент до Data.

## <a name="example"></a>Пример

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

Данные, выделенные с помощью **data_seg** не сохраняют никакой информации о своем расположении.

См. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.

Можно также указать разделы для переменных const ([const_seg](../preprocessor/const-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и функции ([code_seg](../preprocessor/code-seg.md)).

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
