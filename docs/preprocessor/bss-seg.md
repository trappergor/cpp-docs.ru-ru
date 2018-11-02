---
title: bss_seg
ms.date: 10/22/2018
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: 489ced11bb6024fdf9818872c07ab7feebfeabf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566313"
---
# <a name="bssseg"></a>bss_seg

Задает сегмент, в котором неинициализированные переменные сохраняются в OBJ-файле.

## <a name="syntax"></a>Синтаксис

```
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Параметры

**push**<br/>
(Необязательно) Помещает запись во внутреннем стеке компилятора. Объект *pu*sh * могут иметь *идентификатор* и *имя сегмента*.

**pop**<br/>
(Необязательно) Удаление записи из верхней части внутреннего стека компилятора.

*identifier*<br/>
(Необязательно) При использовании с **принудительной**, назначает имя записи во внутреннем стеке компилятора. *Идентификатор* включает несколько записей, извлекаемых с помощью одного **pop** команды. При использовании с **pop**, директива извлекает записи из внутреннего стека до *идентификатор* удаляется; Если *идентификатор* не найден во внутреннем стеке, ничего не извлекается.

*«Имя сегмента»*<br/>
(Необязательно) Имя сегмента. При использовании с **pop**, стек выводится и *имя сегмента* становится активным именем сегмента.

*«Сегмент class»*<br/>
(Необязательно) Включено для совместимости с C++ до версии 2.0. Игнорируется.

## <a name="remarks"></a>Примечания

. OBJ-файлы можно просмотреть при помощи [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию сегмент в OBJ-файле для неинициализированных данных — BSS. В некоторых случаях использование **bss_seg** может ускорить время загрузки благодаря группировке неинициализированных данных в один раздел.

**bss_seg** без параметров сбрасывает сегмент до BSS.

Данные, выделенные с помощью **bss_seg** директива pragma не сохраняют никакой информации о своем расположении.

Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), функции ([code_seg](../preprocessor/code-seg.md)) и переменных const ([const_seg](../preprocessor/const-seg.md)).

См. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.

## <a name="example"></a>Пример

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
