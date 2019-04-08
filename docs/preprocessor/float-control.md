---
title: float_control
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 8a7829252cebb726363c67c990a94d08b0d6467a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032314"
---
# <a name="floatcontrol"></a>float_control

Указывает поведение чисел с плавающей запятой для функции.

## <a name="syntax"></a>Синтаксис

> **#pragma float_control** [ **(** [ *значение* **,** *параметр* [ **, Push-уведомлений** ]] | [ **принудительной** | **pop** ] **)** ]

## <a name="options"></a>Параметры

*значение*, *параметр* [, **принудительной**]<br/>
Указывает поведение чисел с плавающей запятой. *значение* может быть **точное**, **strict**, или **за исключением**. Дополнительные сведения см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md). *Параметр* может быть **на** или **off**.

Если *значение* — **strict**, значения обоих параметров **strict** и **за исключением** задаются *параметр* . **за исключением** может устанавливаться только **на** при **точное** или **strict** задается значение **на**.

Если необязательный **принудительной** маркер добавляется, текущий параметр для *значение* помещается во внутренний стек компилятора.

**push**<br/>
Текущий **float_control** задание на внутреннего стека компилятора

**pop**<br/>
Удаляет **float_control** из верхней части внутреннего стека компилятора и делает это новый **float_control** параметр.

## <a name="remarks"></a>Примечания

Нельзя использовать **float_control** для включения **точное** отключить **за исключением** включен. Аналогичным образом **точное** не может быть выключен, когда [fenv_access](../preprocessor/fenv-access.md) включен. Чтобы перейти от строгой модели к быстродействующей с помощью **float_control** pragma, используйте следующий код:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Чтобы перейти от быстродействующей модели к строгой с **float_control** pragma, используйте следующий код:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Если параметры не указаны, **float_control** не оказывает влияния.

Другие типы директив pragma для значений с плавающей запятой:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Пример

Ниже приведен пример, как перехватить исключение переполнения с плавающей запятой с помощью директивы pragma **float_control**.

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
