---
title: /X (Отклонение стандартных путей включения)
ms.date: 11/04/2016
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 23942803ae0a25aaddd7f5844b303528c2c7ccb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663766"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Отклонение стандартных путей включения)

Запрещает компилятору поиск включаемых файлов в каталогах, указанных в переменных среды PATH и INCLUDE.

## <a name="syntax"></a>Синтаксис

```
/X
```

## <a name="remarks"></a>Примечания

Можно использовать этот параметр вместе с [/I (Дополнительные каталоги включаемых файлов)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) параметр.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **препроцессор** страницу свойств.

1. Изменить **отклонение стандартных путей включения** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Пример

В следующей команде `/X` указывает компилятору игнорировать расположений, указанных в переменных среды PATH и INCLUDE и `/I` указывает каталог, в которой необходимо искать включаемые файлы:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)