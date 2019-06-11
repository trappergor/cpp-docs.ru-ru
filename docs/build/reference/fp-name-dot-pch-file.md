---
title: /Fp (имя &period;PCH-файл)
description: Параметр компилятора/FP позволяет указать имя файла предкомпилированного заголовка.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: 6e7faa934d14acb5d129173c5e0c7ee67d6caf2b
ms.sourcegitcommit: 540fa2f5015de1adfa7b6bf823f6eb4ed5a6a4bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "66460877"
---
# <a name="fp-name-periodpch-file"></a>/Fp (имя &period;PCH-файл)

Предоставляет путь для предкомпилированного заголовка, вместо того чтобы использовать имя пути по умолчанию.

## <a name="syntax"></a>Синтаксис

> **/ Fp**<em>pathname</em>

## <a name="remarks"></a>Примечания

Используйте **/FP** с параметром [/Yc (создать предкомпилированный заголовочный файл)](yc-create-precompiled-header-file.md) или [/Yu (использование файла предкомпилированного заголовка)](yu-use-precompiled-header-file.md) чтобы указать путь и имя файла для предкомпилированного заголовка (PCH) файл. По умолчанию **/Yc** параметр создает имя файла предкомпилированного Заголовка, используя базовое имя файла исходного кода и *pch* расширения.

Если не указать расширение как часть *pathname*, расширение *pch* предполагается, что. При указании имени каталога с помощью косой черты ( **/** ) в конце *pathname*, имя файла по умолчанию — vc*версии*0.pch, где  *версия* является основной номер версии набора инструментов Visual Studio. Этот каталог должен существовать, или создается ошибка C1083.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте **свойства конфигурации** > **C /C++**  > **предкомпилированные заголовки** страницу свойств.

1. Изменить **выходного файла предкомпилированного заголовка** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Примеры

Для создания отдельного именованного версию файла предкомпилированного заголовка для отладочной сборки программы, такие как можно указать команду:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

Следующая команда задает использование файла предкомпилированного заголовка с именем MYPCH.pch. Компилятор выполняет предварительную компиляцию исходного кода в PROG.cpp до конца MYAPP.h и помещает в MYPCH.pch предварительно скомпилированный код. Затем использует содержимое файла MYPCH.pch и компилирует остаток PROG.cpp для создания OBJ-файл. Выходные данные этого примера является файл с именем PROG.exe.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Указание пути](specifying-the-pathname.md)
