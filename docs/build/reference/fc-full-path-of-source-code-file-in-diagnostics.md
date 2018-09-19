---
title: -FC (полный путь к файлу исходного кода в диагностике) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs:
- C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d34fe85354d218d2499dbece70964c2e55e2592
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702711"
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

- compiler_option_FC.cpp(5): ошибка C2143: синтаксическая ошибка: отсутствует «;» перед "}"

С помощью **/FC**, диагностическое будет выглядеть примерно следующим образом диагностики:

- c:\test\compiler_option_fc.cpp(5): ошибка C2143: синтаксическая ошибка: отсутствует «;» перед "}"

**/FC** требуется также в том случае, если вы хотите увидеть полный путь к имени файла, при использовании &#95; &#95;ФАЙЛ&#95; &#95; макрос. См. в разделе [предустановленные макросы](../../preprocessor/predefined-macros.md) Дополнительные сведения о &#95; &#95;ФАЙЛ&#95;&#95;.

**/FC** подразумевается параметр **/ZI**. Дополнительные сведения о **/ZI**, см. в разделе [/Z7, / Zi, /ZI (формат отладочной информации)](../../build/reference/z7-zi-zi-debug-information-format.md).

**/FC** выводит полные пути, задаваемый в нижнем регистре.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Дополнительно** страницу свойств.

1. Изменить **использовать полные пути** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
