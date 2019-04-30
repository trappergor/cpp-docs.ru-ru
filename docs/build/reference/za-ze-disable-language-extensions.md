---
title: /Za, /Ze (отключить расширения языка)
ms.date: 02/19/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: 1db1dbdba4829ccf939cdc4f07ccfefe2474a35d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315889"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (отключить расширения языка)

**/Za** отключает параметр компилятора и выдает ошибки для расширения Майкрософт для C, которые не совместимы с ANSI C89/ISO C90. Устаревший **/Ze** параметр компилятора включает расширения Microsoft. Расширения Microsoft по умолчанию включены.

## <a name="syntax"></a>Синтаксис

> **/Za**<br/>
> **/Ze**

## <a name="remarks"></a>Примечания

> [!NOTE]
> Использование **/Za** при компиляции кода как C++ не рекомендуется. **/Ze** параметр является устаревшим, так как его поведение включено по умолчанию. Список параметров компилятора, см. в разделе [нерекомендуемые и удаленные компилятора параметры](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options).

Компилятор Microsoft C/C++ поддерживает компиляцию кода C одним из двух способов:

- Компилятор использует режим компиляции C по умолчанию, если в файле источника имеется *.c* расширения, или когда [/Tc](tc-tp-tc-tp-specify-source-file-type.md) или [/TC](tc-tp-tc-tp-specify-source-file-type.md) параметра. Компилятор C не C89/C90 компилятора, который по умолчанию включает расширения Microsoft для языка C. Дополнительные сведения о конкретных расширениях см. в разделе [расширения Майкрософт для языков C и C++](microsoft-extensions-to-c-and-cpp.md). При компиляции обоих C и **/Za** указан параметр, компилятор C строго соответствует стандарту C89/C90. Компилятор обрабатывает расширенные ключевые слова как простые идентификаторы Майкрософт, отключает расширения Microsoft и автоматически определяет [ \_ \_STDC\_ \_ ](../../preprocessor/predefined-macros.md) предопределенные макрос для программ C.

- Компилятор смог скомпилировать код C в режиме компиляции C++. Это поведение по умолчанию для исходных файлов, у которых нет *.c* расширения и когда [/Tp](tc-tp-tc-tp-specify-source-file-type.md) или [/TP](tc-tp-tc-tp-specify-source-file-type.md) параметра. В режиме компиляции C++ компилятор поддерживает те части стандартов ISO C99 и C11, которые могут быть включены в стандарт языка C++. Практически весь код C также является допустимым кодом C++. Небольшое количество ключевых слов C и конструкций кода не являются допустимым кодом C++ или интерпретируются по-разному в C++. Компилятор ведет себя в соответствии со стандартом языка C++ в таких случаях. В режиме компиляции C++ **/Za** параметр может привести к непредвиденному поведению и не рекомендуется.

Другие параметры компилятора может повлиять на том, как компилятор обеспечивает соответствие стандартам. Способы задания определенные стандартные параметры поведения C и C++, см. в разделе [/Zc](zc-conformance.md) параметр компилятора. Дополнительные параметры соответствием стандарту C++, см. в разделе [/ permissive-](permissive-standards-conformance.md) и [/std](std-specify-language-standard-version.md) параметры компилятора.

Дополнительные сведения о вопросах соответствия в Visual C++, см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В области навигации выберите **свойства конфигурации** > **C/C++** > **языка**.

1. Изменить **отключить расширения языка** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](compiler-options.md)<br/>
[/Zc (соответствие)](zc-conformance.md)<br/>
[/permissive- (соответствие стандартам)](permissive-standards-conformance.md)<br/>
[/std (определение стандартной версии языка)](std-specify-language-standard-version.md)<br/>
