---
title: /I (Дополнительные каталоги включения)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: 6ec8b15e77fec5214013c484e617904ed29e8197
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270146"
---
# <a name="i-additional-include-directories"></a>/I (Дополнительные каталоги включения)

Добавляет каталог к списку каталогов для поиска включаемых файлов.

## <a name="syntax"></a>Синтаксис

> **/I**[]*каталога*

### <a name="arguments"></a>Аргументы

*Каталог*<br/>
Каталог для добавления в список каталогов для поиска включаемых файлов.

## <a name="remarks"></a>Примечания

Чтобы добавить несколько каталогов, используйте этот параметр несколько раз. Поиск каталогов выполняется только в том случае, пока не будет найден указанного включаемого файла.

Можно использовать этот параметр с параметром ([/X (отклонение стандартных путей включения)](x-ignore-standard-include-paths.md)) параметр.

Компилятор выполняет поиск каталогов в следующем порядке:

1. Если указан с помощью [#include](../../preprocessor/hash-include-directive-c-cpp.md) в форме двойных кавычек, сначала выполняется поиск локальных каталогов. Поиск начинается в тот же каталог, что файл, содержащий **#include** инструкции. Если это не удается найти файл, он выполняет поиск в каталогах открытых в данный момент включаемых файлов, в обратном порядке, в котором они были открыты. Поиск начинается в каталоге родительского включаемого файла, а затем выполняется в каталогах всех включаемых файлов-прародителей.

1. Если указан с помощью **#include** директивы в угловых скобок формы, или если произошел сбой поиска локальный каталог, он ищет каталоги, указанные с помощью **/I** параметр, в том порядке, в котором их находит CL в командной строке.

1. Каталоги, указанные в **INCLUDE** переменной среды.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Общие** страницу свойств.

1. Изменить **Дополнительные каталоги включаемых файлов** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Пример

Следующая команда выполняет поиск включаемых файлов, запрашиваемые MAIN.c в следующем порядке: Во-первых Если указан с помощью двойные кавычки, производится поиск локальных файлов. Затем поиск продолжается в каталог \INCLUDE, а затем в каталоге \MY\INCLUDE и наконец в каталогах, назначенных для переменной среды INCLUDE.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
