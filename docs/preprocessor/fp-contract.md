---
title: fp_contract
ms.date: 03/12/2018
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
ms.openlocfilehash: 14c3ac60d4fc0f45fcf0ece6c3f73153e5de4271
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476509"
---
# <a name="fpcontract"></a>fp_contract

Определяет, выполняется ли сокращения с плавающей запятой. С плавающей запятой сокращением является инструкцией, например FMA (Fused-Multiply Add), которая объединяет две отдельные операции с плавающей запятой в одной инструкции. Использование этих инструкций может повлиять на точности с плавающей запятой, поскольку вместо округления после каждой операции обработчик может округлять выполнять действия только один раз, после выполнения обеих операций.

## <a name="syntax"></a>Синтаксис

> **#pragma fp_contract (** { **на** | **off** } **)**

## <a name="remarks"></a>Примечания

По умолчанию **fp_contract** — **на**. Это указывает компилятору использовать инструкции с плавающей запятой сокращения, где это возможно. Задайте **fp_contract** для **off** для сохранения отдельных инструкций с плавающей запятой.

Дополнительные сведения о поведения с плавающей запятой, см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Другие типы директив pragma для значений с плавающей запятой:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Пример

Код, созданный из этого примера не использует инструкцию совмещенного multiply add даже в том случае, если он доступен на целевом процессоре. Если закомментировать строку `#pragma fp_contract (off)`, созданный код может использовать инструкцию совмещенного multiply add, если таковой имеется.

```cpp
// pragma_directive_fp_contract.cpp
// on x86 and x64 compile with: /O2 /fp:fast /arch:AVX2
// other platforms compile with: /O2

#include <stdio.h>

// remove the following line to enable FP contractions
#pragma fp_contract (off)

int main() {
   double z, b, t;

   for (int i = 0; i < 10; i++) {
      b = i * 5.5;
      t = i * 56.025;

      z = t * i + b;
      printf("out = %.15e\n", z);
   }
}
```

```Output
out = 0.000000000000000e+00
out = 6.152500000000000e+01
out = 2.351000000000000e+02
out = 5.207249999999999e+02
out = 9.184000000000000e+02
out = 1.428125000000000e+03
out = 2.049900000000000e+03
out = 2.783725000000000e+03
out = 3.629600000000000e+03
out = 4.587525000000000e+03
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
