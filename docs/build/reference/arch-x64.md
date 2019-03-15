---
title: /arch (x64)
ms.date: 11/04/2016
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
ms.openlocfilehash: c515307ee3a49ef746eea939e90d7aecbd661b95
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809318"
---
# <a name="arch-x64"></a>/arch (x64)

Задает архитектуру для создания кода на платформе x64. Также см. в разделе [/arch (x86)](arch-x86.md) и [/arch (ARM)](arch-arm.md).

## <a name="syntax"></a>Синтаксис

```
/arch:[AVX|AVX2]
```

## <a name="arguments"></a>Аргументы

**/ arch: AVX**<br/>
Позволяет использовать инструкции Intel AVX.

**/ arch: avx2**<br/>
Позволяет использовать инструкции Intel AVX 2.

## <a name="remarks"></a>Примечания

**/ arch** только влияет на создание кода для собственных функций. При использовании [/CLR](clr-common-language-runtime-compilation.md) для компиляции, **/arch** не влияет на создание кода для управляемых функций.

`__AVX__` Определен символ препроцессора при **/arch: AVX** указан параметр компилятора. `__AVX2__` Определен символ препроцессора при **/arch: avx2** указан параметр компилятора. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md). **/Arch: avx2** параметр появился в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.

### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>Установка параметра компилятора /arch:AVX или /arch:AVX2 в Visual Studio

1. Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации**, **C/C++** папки.

1. Выберите **создание кода** страницу свойств.

1. В **включить расширенный набор инструкций** раскрывающегося списка выберите **расширения Advanced Vector Extensions (/ arch: AVX)** или **Advanced Vector Extensions 2 (/ arch: AVX2)**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>См. также

[/arch (минимальная архитектура ЦПУ)](arch-minimum-cpu-architecture.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
