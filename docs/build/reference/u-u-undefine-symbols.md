---
title: /U, /u (отмена определения символов)
description: Чтобы отменить символы препроцессора, используйте параметры компилятора Microsoft C/C++/U и/u.
ms.date: 09/03/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
ms.openlocfilehash: 78effabba2fa72e5ab7f2dfc6ef91f22383b063f
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609193"
---
# <a name="u-u-undefine-symbols"></a>/U, /u (отмена определения символов)

Параметр компилятора отменяет **`/U`** Определение указанного символа препроцессора. Параметр компилятора отменяет **`/u`** Определение символов, определяемых компилятором для Microsoft.

## <a name="syntax"></a>Синтаксис

> **`/U`**\[ ]*символ*\
> **`/u`**

## <a name="arguments"></a>Аргументы

*знак*<br/>
Символ препроцессора для деопределения.

## <a name="remarks"></a>Примечания

Ни один из **`/U`** параметров и не **`/u`** может отменить определение символа, созданного с помощью **`#define`** директивы.

**`/U`** Параметр может отменить определение символа, который ранее был определен с помощью **`/D`** параметра.

По умолчанию компилятор может определить большое количество символов, характерных для Microsoft. Ниже приведены некоторые распространенные из них.

| Символ | Функция |
|--|--|
| `_CHAR_UNSIGNED` | Тип char по умолчанию не подписан. Определяется при [`/J`](j-default-char-type-is-unsigned.md) указании параметра. |
| `_CPPRTTI` | Определяется для кода, скомпилированного с [`/GR`](gr-enable-run-time-type-information.md) параметром. |
| `_CPPUNWIND` | Определяется для кода, скомпилированного с [`/EHsc`](eh-exception-handling-model.md) параметром. |
| `_DLL` | Определяется при [`/MD`](md-mt-ld-use-run-time-library.md) указании параметра. |
| `_M_IX86` | По умолчанию для целевых объектов x86 определено значение 600. |
| `_MSC_VER` | Определяется как уникальное целочисленное значение для каждой версии компилятора. Дополнительные сведения см. в разделе [стандартные макросы](../../preprocessor/predefined-macros.md). |
| `_WIN32` | Определено для приложений WIN32. Определяется всегда. |
| `_MT` | Определяется, если [`/MD`](md-mt-ld-use-run-time-library.md) [`/MT`](md-mt-ld-use-run-time-library.md) указан параметр или. |

Полный список предварительно определенных макросов для Microsoft см. в разделе [предопределенные макросы](../../preprocessor/predefined-macros.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств свойства **конфигурации**  >  **C/C++**  >  **Дополнительно** .

1. Измените свойства **Отменить определения препроцессора** или **отменить определение всех определений препроцессора** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. описания свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[**`/J`** (Тип char по умолчанию не подписан)](j-default-char-type-is-unsigned.md)<br/>
[**`/GR`** (Включить сведения о типах времени выполнения)](gr-enable-run-time-type-information.md)<br/>
[**`/EH`** (Модель обработки исключений)](eh-exception-handling-model.md)<br/>
[**`/MD`**, **`/MT`** , **`/LD`** (Использовать библиотеку времени выполнения)](md-mt-ld-use-run-time-library.md)
