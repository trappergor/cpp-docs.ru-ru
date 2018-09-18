---
title: -Fo (имя объектного файла) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ab671cbae276796ce89ec12cecbc16334e234e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724266"
---
# <a name="fo-object-file-name"></a>/Fo (имя объектного файла)

Указывает имя файла или каталога объектного файла (OBJ), которое следует использовать вместо имени по умолчанию.

## <a name="syntax"></a>Синтаксис

```
/Fopathname
```

## <a name="remarks"></a>Примечания

Если вы не используете этот параметр, в файле объекта используется базовое имя исходного файла и расширение OBJ. Можно использовать любое имя и расширение, но Рекомендуемое соглашение заключается в использовании. obj.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Откройте страницу свойств **Выходные файлы** .

1. Изменить **имя объектного файла** свойство.  В среде разработки объектный файл должен иметь расширение. obj.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.

## <a name="example"></a>Пример

Следующая команда создает объектный файл с именем this.obj: в существующий каталог, \OBJECT на диске B.

```
CL /FoB:\OBJECT\ THIS.C
```

## <a name="see-also"></a>См. также

[Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)
[параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Указание пути](../../build/reference/specifying-the-pathname.md)