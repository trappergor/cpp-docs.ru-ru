---
title: /X (Отклонение стандартных путей включения)
ms.date: 07/18/2019
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 16f903b98d69472fe1a33b084fe6393ecf9ec001
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341050"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Отклонение стандартных путей включения)

Предотвращает Поиск включаемых файлов в каталогах, указанных в переменных среды PATH и INCLUDE, компилятором.

## <a name="syntax"></a>Синтаксис

```
/X
```

## <a name="remarks"></a>Примечания

Этот параметр можно использовать с параметром [/i (дополнительные каталоги включаемых каталогов)](i-additional-include-directories.md) ( **/i**`directory`).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Щелкните страницу  свойств препроцессора.

1. Измените свойство " **игнорировать стандартные включаемые пути** ".

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Пример

В следующей команде `/X` указывает компилятору игнорировать расположения, указанные в переменных среды PATH и include, и `/I` указывает каталог, в котором следует искать включаемые файлы:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
