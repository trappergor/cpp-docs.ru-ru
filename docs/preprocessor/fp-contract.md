---
title: fp_contract | Документы Microsoft
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 514b4708129d625ea7880e4c61be22c4b1ac2db5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="fpcontract"></a>fp_contract

Определяет, выполняется ли сокращением с плавающей запятой. Сокращение чисел с плавающей является инструкцией, например FMA (Fused-умножения-добавить), который объединяет два отдельных операций с плавающей запятой в одной инструкции. Использование этих инструкций может повлиять на точность чисел с плавающей запятой, поскольку вместо округления после каждой операции обработчик может правило округления только один раз после выполнения обеих операций.

## <a name="syntax"></a>Синтаксис

> **#pragma fp_contract (** { **на** | **off** } **)**  

## <a name="remarks"></a>Примечания  

По умолчанию **fp_contract** — **на**. Это дает компилятору использовать инструкции сокращение чисел с плавающей, где это возможно. Задать **fp_contract** для **off** для сохранения отдельных инструкций с плавающей запятой.

Дополнительные сведения о работе с плавающей запятой см. в разделе [/FP (указать поведение с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).

Другие типы директив pragma для значений с плавающей запятой:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Пример

Код, созданный в этом примере не использует инструкцию совмещенного умножения сложения даже в том случае, если он доступен на целевой процессор. Если закомментировать строку `#pragma fp_contract (off)`, созданный код может использовать инструкцию совмещенного умножения сложения, если он доступен.  
  
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
