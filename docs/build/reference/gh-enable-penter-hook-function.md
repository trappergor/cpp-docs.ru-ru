---
title: /Gh (включение функции-обработчика _penter)
description: Описывает параметр компилятора/GH для вызова предоставляемой функции _penter.
ms.date: 07/06/2020
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 96597d964e6a341aa25f4d52d34974949eb7b096
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058585"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (включение функции-обработчика _penter)

Вызывает `_penter` функцию в начале каждого метода или функции.

## <a name="syntax"></a>Синтаксис

> **`/Gh`**

## <a name="remarks"></a>Примечания

`_penter`Функция не является частью какой бы то ни было библиотеки. Вы можете предоставить определение для `_penter` .

Если вы не планируете явно вызывать `_penter` , вам не нужно предоставлять прототип. Функция должна отправить содержимое всех регистров на вход и открыть неизмененное содержимое при выходе. Оно должно выглядеть так, как если бы оно имело следующий прототип:

```cpp
void __declspec(naked) __cdecl _penter( void );
```

Это объявление недоступно для 64-разрядных проектов.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте страницу свойств **конфигурации**  >  **C/C++**  >  **Командная строка** .

1. В поле **Дополнительные параметры** введите параметр компилятора.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

Следующий код, скомпилированный с помощью **/GH**, показывает, как `_penter` вызывается дважды. один раз при вводе функции `main` и один раз при вводе функции `x` . Пример состоит из двух исходных файлов, которые компилируются отдельно.

```cpp
// local_penter.cpp
// compile with: cl /EHsc /c local_penter.cpp
// processor: x86
#include <stdio.h>

extern "C" void __declspec(naked) __cdecl _penter( void ) {
   _asm {
      push eax
      push ebx
      push ecx
      push edx
      push ebp
      push edi
      push esi
    }

   printf_s("\nIn a function!");

   _asm {
      pop esi
      pop edi
      pop ebp
      pop edx
      pop ecx
      pop ebx
      pop eax
      ret
    }
}
```

```cpp
// Gh_compiler_option.cpp
// compile with: cl /EHsc /Gh Gh_compiler_option.cpp local_penter.obj
// processor: x86
#include <stdio.h>

void x() {}

int main() {
   x();
}
```

При запуске локальная `_penter` функция вызывается при входе в `main` и `x` :

```Output

In a function!
In a function!
```

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[`/GH`(Включить функцию-обработчик _pexit)](gh-enable-pexit-hook-function.md)
