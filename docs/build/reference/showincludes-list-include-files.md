---
title: /showIncludes (список включаемых файлов)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
ms.openlocfilehash: 7be3d93f91133ad1a29e6b4d6d2c50157a3376b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523049"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (список включаемых файлов)

Компилятор выводит список включаемых файлов. Вложенные включают файлы также являются отображаемые (файлы, включенные файлы, которые включены).

## <a name="syntax"></a>Синтаксис

```
/showIncludes
```

## <a name="remarks"></a>Примечания

Если включаемый файл встречается во время компиляции, выводится сообщение, например:

```
Note: including file: d:\MyDir\include\stdio.h
```

Вложенные включают файлы обозначаются отступа, одно пространство для каждого уровня вложения, например:

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

В этом случае `2.h` был включен в `1.h`, поэтому отступы.

**/Showincludes** предоставляет параметр `stderr`, а не `stdout`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **Показывать включаемые файлы** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)