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
ms.openlocfilehash: bf7734a7b81c9550c060d43c2eabf5cb05332407
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820537"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (Включение функции обработчика _penter)

Приводит к вызову `_penter` функции в начале каждого метода или функции.

## <a name="syntax"></a>Синтаксис

```
/Gh
```

## <a name="remarks"></a>Примечания

`_penter` Функция не является частью любой библиотеки, и это необходимо указать определение `_penter`.

Если вы не планируете явным образом вызвать `_penter`, не нужно предоставлять прототип. Функция должна выглядеть так, как если бы она имела следующий прототип, и он должен отправка содержимого регистров на запись и отображение без изменений содержимого при выходе:

```
void __declspec(naked) __cdecl _penter( void );
```

Это объявление не доступен для 64-разрядных проектов.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

В следующем коде, при компиляции с **/Gh**, показано, как `_penter` вызывается дважды; один раз при вводе функции `main` и один раз при вводе функции `x`.

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

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
