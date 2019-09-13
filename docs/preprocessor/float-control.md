---
title: Прагма float_control
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: aa8cdc07953405175c1753791ab53214d73ba516
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218577"
---
# <a name="float_control-pragma"></a>Прагма float_control

Указывает поведение чисел с плавающей запятой для функции.

## <a name="syntax"></a>Синтаксис

> **#pragma float_control**\
> **#pragma float_control (** { **точных** | **строго** |  **,** **Кроме** }, { **On** | **Off** } [ **, Push** ] **)** \
> **#pragma float_control (** { **Push** | **POP** } **)**

## <a name="options"></a>Параметры

**Точная** **строгость** **, за**исключением отключения, принудительной отправки |  |  | \
Задает поведение с плавающей запятой, которое может быть **точным**, **строго**илиисключим. Дополнительные сведения см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md). Параметр может иметь значение **On** или **Off**.

Если задано значение " **умеренный**", параметры как для параметра " **ограничивать** " , так и **за исключением** задаются параметром " **вкл** . параметр **except** может иметь значение **On** , только если для параметра **Точная** или **строго** задано значение **On**.

Если добавляется Необязательный токен **Push** , текущее значение параметра **float_control** помещается во внутренний стек компилятора.

**распространение**\
Передача текущего параметра **float_control** во внутренний стек компилятора

**Рор**\
Удаляет параметр **float_control** из верхнего внутреннего стека компилятора и создает новый параметр **float_control** .

## <a name="remarks"></a>Примечания

Нельзя использовать **float_control** для включения **точной точности** , если включен параметр **except** . Точно так же нельзя отключить функцию **точной** , если включена [fenv_access](../preprocessor/fenv-access.md) . Чтобы переходить от модели к быстрой модели с помощью директивы pragma **float_control** , используйте следующий код:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Для перехода от быстрой модели к модели с помощью директивы pragma **float_control** используйте следующий код:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Если параметры не указаны, **float_control** не оказывает никакого влияния.

Другие типы директив pragma для значений с плавающей запятой:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Пример

В следующем примере показано, как перехватить исключение переполнения с плавающей запятой с помощью директивы pragma **float_control**.

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

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
