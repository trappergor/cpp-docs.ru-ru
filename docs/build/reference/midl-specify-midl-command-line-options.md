---
title: -MIDL (указание параметров командной строки MIDL) | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce4c5159a66963268ae83e0c0adfdc082dfcc81c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706944"
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

2. Выберите **свойства конфигурации** > **компоновщика** > **внедренные IDL** страницу свойств.

3. Изменить **MIDL-команды** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[/ IDLOUT (имен выходным файлам MIDL)](../../build/reference/idlout-name-midl-output-files.md)
[/IGNOREIDL (не процесса атрибуты в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)
 [ /TLBOUT (имя. TLB-файл)](../../build/reference/tlbout-name-dot-tlb-file.md)
[сборка Атрибутированной программы](../../windows/building-an-attributed-program.md)