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
ms.openlocfilehash: 9a2584591f6ca22d6767a5c447ffb72bea0a78ea
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825879"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (отключить расширения языка)

Параметр компилятора **/Za** отключает и выдает ошибки для расширений Майкрософт в C, которые несовместимы с ANSI C89/ISO C90. Нерекомендуемый параметр компилятора **/Ze** включает расширения Майкрософт. Расширения Microsoft по умолчанию включены.

## <a name="syntax"></a>Синтаксис

> **/ZA**\
> **/Ze**

## <a name="remarks"></a>Примечания

> [!NOTE]
> Использование параметра **/Za** при компиляции кода в качестве языка C++ не рекомендуется. Параметр **/Ze** является устаревшим, так как его поведение включено по умолчанию. Список устаревших параметров компилятора см. в разделе [устаревшие и удаленные параметры компилятора](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options).

Компилятор Microsoft C/C++ поддерживает компиляцию кода C двумя способами:

- Компилятор использует режим компиляции C по умолчанию, если исходный файл имеет расширение *C* или если указан параметр [/TC](tc-tp-tc-tp-specify-source-file-type.md) или [/TC](tc-tp-tc-tp-specify-source-file-type.md) . Компилятор C является компилятором C89/C90, который по умолчанию включает расширения Майкрософт для языка C. Дополнительные сведения о конкретных расширениях см. [в разделе расширения Майкрософт для C и C++](microsoft-extensions-to-c-and-cpp.md). При указании как компиляции C, так и параметра **/Za** компилятор языка c строго соответствует стандарту C89/C90. Компилятор рассматривает расширенные ключевые слова Майкрософт как простые идентификаторы, отключает другие расширения Майкрософт и автоматически определяет [ \_ \_\_ ](../../preprocessor/predefined-macros.md) предопределенный макрос STDC для программ на языке C.

- Компилятор может компилировать код C в режиме компиляции C++. Это поведение используется по умолчанию для исходных файлов, у которых нет расширения *c* , а также при указании параметра [/TP](tc-tp-tc-tp-specify-source-file-type.md) или [/TP](tc-tp-tc-tp-specify-source-file-type.md) . В режиме компиляции C++ компилятор поддерживает такие части стандартов ISO C99 и C11, которые были включены в стандарт C++. Почти весь код на языке C также является допустимым кодом C++. Небольшое количество ключевых слов и конструкций кода на языке C не является допустимым кодом C++ или интерпретируется иначе в C++. В этих случаях компилятор ведет себя в соответствии со стандартом C++. В режиме компиляции C++ параметр **/Za** может привести к непредвиденному поведению и не рекомендуется.

Другие параметры компилятора могут влиять на то, как компилятор гарантирует соответствие стандартам. Способы указания конкретных стандартных параметров поведения C и C++ см. в разделе параметр компилятора [/Zc](zc-conformance.md) . Дополнительные параметры соответствия C++ Standard см. в разделе Параметры компилятора [/permissive-](permissive-standards-conformance.md) и [/std](std-specify-language-standard-version.md) .

Дополнительные сведения о проблемах соответствия с Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. В области навигации выберите **Свойства** > конфигурации**язык****C/C++** > .

1. Измените свойство **Отключить расширения языка** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора](compiler-options.md)<br/>
[/Zc (соответствие)](zc-conformance.md)<br/>
[/permissive- (соответствие стандартам)](permissive-standards-conformance.md)<br/>
[/STD (Указание версии стандарта Language Standard)](std-specify-language-standard-version.md)<br/>
