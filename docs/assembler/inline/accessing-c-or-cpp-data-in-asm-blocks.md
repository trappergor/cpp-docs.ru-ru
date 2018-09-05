---
title: Доступ к данным C или C++ в блоках __asm | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9e4b684c878e630de81ac712fab714dc09db5ff
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685041"
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>Доступ к данным C или C++ в блоках __asm

**Блок, относящийся только к системам Microsoft**

Большое удобство встроенного кода на языке ассемблера — это возможность ссылаться на переменные C или C++ по имени. В блоке `__asm` можно обращаться ко всем символам, включая имена переменных из области видимости, в которой находится этот блок. Например, если переменная C `var` находится в области видимости, инструкция

```cpp
__asm mov eax, var
```

сохраняет значение переменной `var` в регистре EAX.

Если для класса, структуры или члена объединения имеет уникальное имя, `__asm` блок могут ссылаться на нее с помощью только имя члена, без указания переменной или `typedef` имя перед точкой (**.**) оператор. Однако если имя члена не является уникальным, необходимо поместить переменную или имя `typedef` непосредственно перед оператором точки. Например, в типах структур в следующем примере в качестве имен членов используется общее имя `same_name`.

Если переменные объявлены с типами

```cpp
struct first_type hal;
struct second_type oat;
```

во всех ссылках на член `same_name` необходимо указывать имя переменной, поскольку имя `same_name` не является уникальным. Однако имя члена `weasel` уникально, поэтому на него можно ссылаться, используя только имя члена:

```cpp
// InlineAssembler_Accessing_C_asm_Blocks.cpp
// processor: x86
#include <stdio.h>
struct first_type
{
   char *weasel;
   int same_name;
};

struct second_type
{
   int wonton;
   long same_name;
};

int main()
{
   struct first_type hal;
   struct second_type oat;

   __asm
   {
      lea ebx, hal
      mov ecx, [ebx]hal.same_name ; Must use 'hal'
      mov esi, [ebx].weasel       ; Can omit 'hal'
   }
   return 0;
}
```

Обратите внимание, что возможность не указывать имя переменной — это всего лишь вопрос удобства при написании кода. Создаваемые инструкции ассемблера не зависят от наличия или отсутствия имени переменной.

В C++ доступ к данным-членам возможен без учета ограничений доступа. Однако вызов функций-членов невозможен.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>