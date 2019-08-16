---
title: /MIDL (Указание параметров командной строки MIDL)
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: ca172428943d2446490eeb10741966f5e8c9ea85
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492721"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Указание параметров командной строки MIDL)

Указывает файл ответов для параметров командной строки MIDL

## <a name="syntax"></a>Синтаксис

> **/MIDL:\@** <em>файл</em>

## <a name="arguments"></a>Аргументы

*file*<br/>
Имя файла, содержащего [Параметры командной строки MIDL](/windows/win32/Midl/general-midl-command-line-syntax).

## <a name="remarks"></a>Примечания

Все параметры для преобразования IDL-файла в файл TLB должны быть заданы в *файле*. Параметры командной строки MIDL нельзя указывать в командной строке компоновщика. Если/MIDL не указан, компилятор MIDL будет вызываться только с именем IDL-файла и без других параметров.

Файл должен содержать один параметр командной строки MIDL для каждой строки.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств**встроенного IDL** -свойства**компоновщика** >  **Свойства** > конфигурации.

1. Измените свойство **команды MIDL** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[/IDLOUT (присвоение имен выходным файлам MIDL)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (запрет преобразования атрибутов в MIDL)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (именование файла TLB)](tlbout-name-dot-tlb-file.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)
