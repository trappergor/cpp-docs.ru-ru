---
title: /Fd (имя файла базы данных программы)
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: c686de7dc9c9c20c404240db558d2ff66078ceb7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808993"
---
# <a name="fd-program-database-file-name"></a>/Fd (имя файла базы данных программы)

Указывает имя файла для файла базы данных (PDB) программы, созданные [/Z7, / Zi, /ZI (формат отладочной информации)](z7-zi-zi-debug-information-format.md).

## <a name="syntax"></a>Синтаксис

```
/Fdpathname
```

## <a name="remarks"></a>Примечания

Без **/Fd**, по умолчанию используется имя PDB-файла VC*x*0.pdb, где *x* – основная используемая версия Visual C++.

Если указать путь, который не включает имя файла (путь заканчивается обратной косой черты), компилятор создает PDB-файл с именем VC*x*0. PDB-файл в указанном каталоге.

При указании имени файла, который не поддерживает расширения, компилятор использует PDB-файл в качестве расширения.

Этот параметр также имена файла состояния (IDB), используемый для минимального перепостроения и добавочной компиляции.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Откройте страницу свойств **Выходные файлы** .

1. Изменить **имя файла базы данных программы** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.

## <a name="example"></a>Пример

Эта команда создает PDB-файл с именем PROG.pdb и IDB-файла с именем PROG.idb:

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Указание пути](specifying-the-pathname.md)
