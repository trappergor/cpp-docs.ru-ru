---
title: fenv_access
ms.date: 03/12/2018
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: 507e78dd9f9571cc9ce44d7fd91e78b1c955ba73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389259"
---
# <a name="fenvaccess"></a>fenv_access
Отключает (**на**) или включает (**off**) флаг оптимизации, которые могут повлиять на среду с плавающей запятой, тесты и изменения режима.

## <a name="syntax"></a>Синтаксис

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Примечания

По умолчанию **fenv_access** — **off**. Если компилятор можно предположить, что ваш код с ними управлять среду с плавающей запятой, а затем его можно выполнять многие оптимизации код с плавающей запятой. Задайте **fenv_access** для **на** для сообщают компилятору, что код обращается к среде с плавающей запятой для проверки флагов состояния исключения, или задать флаги режима элемента управления. Компилятор отключает этих оптимизаций, таким образом, чтобы ваш код может обращаться к среду с плавающей запятой согласованно.

Дополнительные сведения о поведения с плавающей запятой, см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Виды оптимизации, которые регулируются **fenv_access** являются:

- Глобальное исключение общей части выражения

- Перемещение кода

- Свертывание констант

Другие типы директив pragma для значений с плавающей запятой:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Примеры

В этом примере устанавливается **fenv_access** для **на** задать регистр с плавающей запятой для 24-битной точности:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-003
```

Если закомментировать строку `#pragma fenv_access (on)` из предыдущего примера, обратите внимание на то, что вывод будет отличаться, поскольку компилятор выполняет вычисление во время компиляции, который не используется режим управления.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-002
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
