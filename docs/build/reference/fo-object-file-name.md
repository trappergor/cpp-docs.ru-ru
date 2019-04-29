---
title: /Fo (имя объектного файла)
ms.date: 11/04/2016
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: a8f2c1a196f18e6d310fd41d4dbed751440a4c20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293047"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

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

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Указание пути](specifying-the-pathname.md)
