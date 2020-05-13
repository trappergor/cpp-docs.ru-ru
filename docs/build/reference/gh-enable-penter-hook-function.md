---
title: /Gh (Включение функции обработчика _penter)
ms.date: 11/04/2016
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 87815b5f0e0450b84acbe3c35b7ef4f31216ec72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749290"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (Включение функции обработчика _penter)

Вызывает вызов функции `_penter` в начале каждого метода или функции.

## <a name="syntax"></a>Синтаксис

```
/Gh
```

## <a name="remarks"></a>Remarks

Функция `_penter` не является частью какой-либо библиотеки, и `_penter`это до вас, чтобы предоставить определение для .

Если вы не планируете явно звонить, `_penter`вам не нужно предоставлять прототип. Функция должна отображаться так, как если бы у нее был следующий прототип, и она должна толкать содержимое всех регистров на входе и высвобожда неизмененное содержимое на выходе:

```cpp
void __declspec(naked) __cdecl _penter( void );
```

Эта декларация недоступна для 64-битных проектов.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

Следующий код, когда компилируется `_penter` с **/Gh**, показывает, как называется дважды; один раз `main` при вводе `x`функции и один раз при вводе функции.

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

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

```Output
In a function!
In a function!
```

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
