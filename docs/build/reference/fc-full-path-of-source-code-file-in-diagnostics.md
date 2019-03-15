---
title: /FC (полный путь к файлу исходного кода в папке Diagnostics)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 190174e1e2ac4d160140ddc54f9cc1c3a1b31709
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809032"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (полный путь к файлу исходного кода в папке Diagnostics)

Компилятор для отображения полного пути файлов исходного кода, передаваемые компилятору в диагностике.

## <a name="syntax"></a>Синтаксис

> /FC

## <a name="remarks"></a>Примечания

Рассмотрим следующий код:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Без **/FC**, диагностическое будет выглядеть примерно следующим образом диагностики:

- compiler_option_FC.cpp(5) : error C2143: syntax error : missing ';' before '}'

С помощью **/FC**, диагностическое будет выглядеть примерно следующим образом диагностики:

- c:\test\compiler_option_fc.cpp(5) : error C2143: syntax error : missing ';' before '}'

**/FC** требуется также в том случае, если вы хотите увидеть полный путь к имени файла, при использовании &#95; &#95;ФАЙЛ&#95; &#95; макрос. См. в разделе [предустановленные макросы](../../preprocessor/predefined-macros.md) Дополнительные сведения о &#95; &#95;ФАЙЛ&#95;&#95;.

**/FC** подразумевается параметр **/ZI**. Дополнительные сведения о **/ZI**, см. в разделе [/Z7, / Zi, /ZI (формат отладочной информации)](z7-zi-zi-debug-information-format.md).

**/FC** выводит полные пути, задаваемый в нижнем регистре.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Дополнительно** страницу свойств.

1. Изменить **использовать полные пути** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
