---
title: fenv_access | Документы Microsoft
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74f20b1dcb20c1449d21e91181f8bfb17075b7e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912970"
---
# <a name="fenvaccess"></a>fenv_access

Отключает (**на**) или включает (**off*) оптимизации, которые могут измениться с плавающей запятой среды флаг тесты и изменения режима.

## <a name="syntax"></a>Синтаксис

> **#pragma fenv_access (** { **на** | **off** } **)**  

## <a name="remarks"></a>Примечания

По умолчанию **fenv_access** — **off**. Если компилятор можно предполагать, что код не получить доступ к или управляют средой с плавающей запятой, то он может выполнять многие оптимизации код с плавающей запятой. Задать **fenv_access** для **на** для информирования компилятору, что код обращается к среде с плавающей запятой для тестирования флагов состояния исключения, или задать режим флаги управления. Компилятор отключает эти оптимизации, чтобы ваш код может обращаться к среде с плавающей запятой согласованно. 

Дополнительные сведения о работе с плавающей запятой см. в разделе [/FP (указать поведение с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Виды оптимизации, которые подлежат **fenv_access** являются:

- Глобальное исключение общей части выражения

- Перемещение кода

- Свертка констант

Другие типы директив pragma для значений с плавающей запятой:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Примеры

В этом примере устанавливается **fenv_access** для **на** для задания регистр с плавающей точкой управления для точности в 24-разрядный:

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

Если закомментировать строку `#pragma fenv_access (on)` из предыдущего примера, обратите внимание, что вывод будет отличаться, поскольку компилятор выполняет оценку выражений во время компиляции, который не используется режим управления.

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
