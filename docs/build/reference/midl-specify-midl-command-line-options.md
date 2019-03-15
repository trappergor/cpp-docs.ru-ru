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
ms.openlocfilehash: 584958ac51bdc491ad1bdd16117ecaad6e000ec7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814193"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **внедренные IDL** страницу свойств.

1. Изменить **MIDL-команды** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[/IDLOUT (присвоение имен выходным файлам MIDL)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (запрет преобразования атрибутов в MIDL)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (именование файла TLB)](tlbout-name-dot-tlb-file.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)
