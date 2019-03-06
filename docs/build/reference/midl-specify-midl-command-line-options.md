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
ms.openlocfilehash: 1e1025f4ce5bfd7dfff40a53472ad71870c694e6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412956"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Указание параметров командной строки MIDL)

Задает файл ответов для параметров командной строки MIDL

## <a name="syntax"></a>Синтаксис

> **/ MIDL:\@**<em>файла</em>

## <a name="arguments"></a>Аргументы

*file*<br/>
Имя файла, содержащего [параметров командной строки MIDL](/windows/desktop/Midl/general-midl-command-line-syntax).

## <a name="remarks"></a>Примечания

Все параметры для преобразования IDL-файла TLB-файл, которые должны быть заданы в *файл*; В командной строке компоновщика нельзя использовать параметры командной строки MIDL. Если/MIDL не указан, компилятор MIDL будет вызываться только имя файла IDL и нет других вариантов.

Этот файл должен содержать один параметр командной строки MIDL каждой строки.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **внедренные IDL** страницу свойств.

1. Изменить **MIDL-команды** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[/IDLOUT (присвоение имен выходным файлам MIDL)](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (запрет преобразования атрибутов в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (именование файла TLB)](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)
