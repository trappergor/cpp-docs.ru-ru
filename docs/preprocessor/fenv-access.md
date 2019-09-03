---
title: Прагма fenv_access
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: c8e66881bde12df28bf24e18230471cb4caca792
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218607"
---
# <a name="fenv_access-pragma"></a>Прагма fenv_access

Отключает (**включено**) или включает (**выключенное**) оптимизацию, которая может изменить проверки флагов среды с плавающей точкой и изменения режима.

## <a name="syntax"></a>Синтаксис

> **#pragma fenv_access (** { **On** | **Off** } **)**

## <a name="remarks"></a>Примечания

По умолчанию **fenv_access** **отключен**. Если компилятор может предположить, что код не обращается к среде с плавающей запятой или не манипулирует ею, он может выполнять много операций оптимизации кода с плавающей точкой. Задайте для параметра **fenv_access** значение **On** , чтобы сообщить компилятору, что код получает доступ к среде с плавающей запятой, для проверки флагов состояния, исключений или установки флагов режима управления. Компилятор отключает эти оптимизации, чтобы код мог постоянно обращаться к среде с плавающей запятой.

Дополнительные сведения о поведении чисел с плавающей запятой см. в разделе [/FP (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Ниже приведены виды оптимизации, которые подчиняются **fenv_access** .

- Глобальное исключение общей части выражения

- Перемещение кода

- Свертывание констант

Другие типы директив pragma для значений с плавающей запятой:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Примеры

В этом примере для параметра **fenv_access** устанавливается значение **On** , чтобы задать регистр с контролем операций с плавающей запятой для 24-разрядной точности:

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

Если закомментировать `#pragma fenv_access (on)` предыдущий пример, обратите внимание, что выходные данные отличаются, так как компилятор выполняет вычисление во время компиляции, которое не использует режим управления.

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
