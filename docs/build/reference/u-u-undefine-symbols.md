---
title: Параметры /U и /u (отмена определения символа)
ms.date: 11/04/2016
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
ms.openlocfilehash: bfc03ebd5c900bf8bf81b4a50eed02111baf85ee
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822497"
---
# <a name="u-u-undefine-symbols"></a>Параметры /U и /u (отмена определения символа)

**/U** параметр компилятора отменяет определение заданного символа препроцессора. **/U** параметр компилятора отменяет определение символов для систем Майкрософт, определяемых компилятором.

## <a name="syntax"></a>Синтаксис

```
/U[ ]symbol
/u
```

## <a name="arguments"></a>Аргументы

*Символ*<br/>
Символ препроцессора для отмены определения.

## <a name="remarks"></a>Примечания

Ни **/U** или **/u** может отменить определение символа, созданного с помощью **#define** директива.

**/U** может отменить определение символа, который ранее был определен с помощью **/D** параметр.

По умолчанию компилятор определяет следующие символы характерные для Майкрософт.

|Символ|Функция|
|------------|--------------|
|_CHAR_UNSIGNED|Тип char по умолчанию не подписан. Определяется, если [/j](j-default-char-type-is-unsigned.md) параметра.|
|_CPPRTTI|Определен для кода, компилируемого с [/GR](gr-enable-run-time-type-information.md) параметр.|
|_CPPUNWIND|Определен для кода, компилируемого с [/EHsc](eh-exception-handling-model.md) параметр.|
|_DLL|Определяется, если [/MD](md-mt-ld-use-run-time-library.md) параметра.|
|_M_IX86|По умолчанию, определенные для 600 x86 целевых объектов.|
|_MSC_VER|Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).|
|_WIN32|Определяется для приложений WIN32. Определяется всегда.|
|_MT|Определяется, если [/MD или/MT](md-mt-ld-use-run-time-library.md) параметра.|

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **отменить определения препроцессора** или **отменить все определения препроцессора** свойства.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. описания свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/J (тип символа по умолчанию не подписан)](j-default-char-type-is-unsigned.md)<br/>
[/GR (предоставление информации о типах во время выполнения)](gr-enable-run-time-type-information.md)<br/>
[/EH (модель обработки исключений)](eh-exception-handling-model.md)<br/>
[/MD, /MT, /LD (использование библиотеки времени выполнения)](md-mt-ld-use-run-time-library.md)
