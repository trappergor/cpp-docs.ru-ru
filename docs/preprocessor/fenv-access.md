---
title: Прагма fenv_access
description: Описывает использование и влияние директивы pragma fenv_access. Директива fenv_access управляет доступом к среде с плавающей запятой во время выполнения.
ms.date: 11/19/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: e03eb404f2805a4f7c96509600c063c1b1acf629
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305847"
---
# <a name="fenv_access-pragma"></a>Прагма fenv_access

Отключает (**включено**) или включает (**выключенное**) оптимизацию, которая может изменить проверки флагов среды с плавающей точкой и изменения режима.

## <a name="syntax"></a>Синтаксис

> **fenv_access #pragma (** { **On** | **Off** } **)**

## <a name="remarks"></a>Заметки

По умолчанию **fenv_access** отключен **.** Компилятор предполагает, что ваш код не обращается к среде с плавающей запятой или не управляет ею. Если доступ к среде не требуется, компилятор может повысить эффективность кода с плавающей точкой.

Включите **fenv_access** , если ваш код проверяет флаги состояния с плавающей точкой, исключения или задает флаги режима управления. Компилятор отключает оптимизацию операций с плавающей запятой, поэтому код может постоянно обращаться к среде с плавающей запятой.

Параметр командной строки [/FP: Option] автоматически включает **fenv_access**. Дополнительные сведения об этом и других воздействиех с плавающей запятой см. в разделе [/FP (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Существуют ограничения на способы использования директивы pragma **fenv_access** в сочетании с другими параметрами с плавающей запятой:

- Невозможно включить **fenv_access** , если не включена точная семантика. Точная семантика может быть включена либо директивой pragma [float_control](float-control.md) , либо с помощью параметров компилятора [/FP: точной](../build/reference/fp-specify-floating-point-behavior.md) или [/FP: строго](../build/reference/fp-specify-floating-point-behavior.md) . Компилятор по умолчанию имеет значение **/FP: точнее** , если не указан другой параметр командной строки с плавающей запятой.

- Нельзя использовать **float_control** для отключения точной семантики при установке **fenv_access (on)** .

Ниже приведены виды оптимизации, которые подчиняются **fenv_access** .

- Глобальное исключение общей части выражения

- Перемещение кода

- Свертывание констант

Другие типы директив pragma для значений с плавающей запятой:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Примеры

В этом примере устанавливается **fenv_access** в значение **On** , чтобы задать Контрольный регистр с плавающей запятой для 24-разрядной точности:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2 /arch:IA32
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
out=9.999999776482582e-03
```

Если закомментировать `#pragma fenv_access (on)` из предыдущего примера, выходные данные будут отличаться. Это обусловлено тем, что компилятор выполняет вычисление во время компиляции, которое не использует режим управления.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
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
out=1.000000000000000e-02
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
