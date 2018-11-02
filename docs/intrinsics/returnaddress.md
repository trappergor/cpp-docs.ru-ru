---
title: _ReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: 01916a9306faa4159f54225b745fd56c35b5ae16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641787"
---
# <a name="returnaddress"></a>_ReturnAddress

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

`_ReturnAddress` Предоставляет адрес памяти инструкции в вызывающей функции, который будет выполнен после возврата управления вызывающему объекту.

Создавайте следующие программы и его пошагово в отладчике. При пошаговом выполнении программы, запишите адрес, возвращенный `_ReturnAddress`. Затем, сразу после возврата из функции где `_ReturnAddress` используется, и откройте [как: использование окна дизассемблирования](/visualstudio/debugger/how-to-use-the-disassembly-window) и обратите внимание, что адрес следующую инструкцию для выполнения совпадает с адрес, возвращенный `_ReturnAddress`.

Оптимизацию, например встраивание может повлиять на обратный адрес. Например, если ниже пример программы компилируется с [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` будет подставляться в вызывающей функции — `main`. Таким образом, вызовы `_ReturnAddress` из `inline_func` и `main` каждый будет создавать то же значение.

Когда `_ReturnAddress` используется в программы, скомпилированной с [/CLR](../build/reference/clr-common-language-runtime-compilation.md), функция, содержащая `_ReturnAddress` вызов будет скомпилировать как неуправляемую функцию. Если функция скомпилирована как управляемые вызовы в функцию, содержащую `_ReturnAddress`, `_ReturnAddress` может вести себя непредусмотренным образом.

## <a name="requirements"></a>Требования

**Файл заголовка** \<intrin.h >

## <a name="example"></a>Пример

```
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)