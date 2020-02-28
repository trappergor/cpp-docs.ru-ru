---
title: float_control - прагма
description: Описывает использование и влияние директивы pragma float_control. Директива float_control управляет состоянием точной семантики с плавающей точкой и семантикой исключений во время выполнения.
ms.date: 11/18/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 5f907bfeb3f92f788fe951854ddc32accc83ae03
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78166788"
---
# <a name="float_control-pragma"></a>float_control - прагма

Указывает поведение чисел с плавающей запятой для функции.

## <a name="syntax"></a>Синтаксис

> **#pragma float_control**\
> **#pragma float_control (Точная,** { **On** | **Off** } [ **, Push** ] **)** \
> **#pragma float_control (за исключением** { **On** | **Off** } [ **, Push** ] **)** \
> **float_control #pragma (** { **Push** | **POP** } **)**

## <a name="options"></a>Параметры

**Точная**, **при** |  **отправке**\
Указывает, следует ли включить (**On**) или отключить (**выключить**) точную семантику с плавающей запятой. Сведения о различиях с параметром компилятора **/FP: точную** см. в разделе "Примечания". **Необязательный токен Push отправляет** текущее значение для **float_control** во внутреннем стеке компилятора.

**за исключением** |  **,** **Отправка**\
Указывает, следует ли включить (**On**) или отключить (**Отключить**) семантику исключений с плавающей запятой. **Необязательный токен Push отправляет** текущее значение для **float_control** во внутреннем стеке компилятора.

параметр **except** может иметь значение **On** , только если параметр **точнее** также имеет значение **On**.

**отправка**\
Передает текущий параметр **float_control** в стек внутреннего компилятора.

\ **POP**
Удаляет параметр **float_control** из верхнего внутреннего стека компилятора и создает новый параметр **float_control** .

## <a name="remarks"></a>Remarks

Директива pragma **float_control** не имеет того же поведения, что и параметр компилятора [/FP](../build/reference/fp-specify-floating-point-behavior.md) . Директива pragma **float_control** управляет только частью поведения операций с плавающей запятой. Для повторного создания параметров компилятора **/FP** его необходимо сочетать с директивами pragma [fp_contract](../preprocessor/fp-contract.md) и [fenv_access](../preprocessor/fenv-access.md) . В следующей таблице приведены эквивалентные параметры директивы pragma для каждого параметра компилятора.

| | float_control (Точная \*) | float_control (за исключением \*) | fp_contract (\*) | fenv_access (\*) |
|-|-|-|-|-|
| /FP: не более             | on  | on  | off | on  |
| /FP: точный            | on  | off | on  | off |
| /FP: быстрый               | off | off | on  | off |

Иными словами, может потребоваться использовать несколько директив pragma в сочетании для эмуляции параметров командной строки **/FP: Fast**, **/FP: точных**и **/FP: строго** .

Существуют ограничения на способы использования **float_control** и **fenv_access** сочетания директив pragma с плавающей запятой в сочетании.

- Можно использовать только **float_control** для установки, **за исключением** **On** , если включена точная семантика. Точная семантика может быть включена либо директивой pragma **float_control** , либо с помощью параметров компилятора **/FP: точной** или **/FP: строго** .

- Нельзя использовать **float_control** для включения **точной точности** при включенной семантике исключений, будь то **float_control** pragma или параметр компилятора **/FP: except** .

- Невозможно включить **fenv_access** , если не включена точная семантика, независимо от того, является ли директива pragma **float_control** или параметром компилятора.

- Вы не можете использовать **float_control** , чтобы включить **точную** настройку при включенном **fenv_access** .

Эти ограничения означают, что порядок некоторых директив pragma с плавающей точкой важен. Для перехода от быстрой модели к модели с помощью директив pragma используйте следующий код:

```cpp
#pragma float_control(precise, on)  // enable precise semantics
#pragma fenv_access(on)             // enable environment sensitivity
#pragma float_control(except, on)   // enable exception semantics
#pragma fp_contract(off)            // disable contractions
```

Чтобы переходить от модели к быстрой модели с помощью **float_control** директивы pragma, используйте следующий код:

```cpp
#pragma float_control(except, off)  // disable exception semantics
#pragma fenv_access(off)            // disable environment sensitivity
#pragma float_control(precise, off) // disable precise semantics
#pragma fp_contract(on)             // enable contractions
```

Если параметры не указаны, **float_control** не оказывает никакого влияния.

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

## <a name="see-also"></a>См. также раздел

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[fenv_access](../preprocessor/fenv-access.md)\
[fp_contract](../preprocessor/fp-contract.md)
