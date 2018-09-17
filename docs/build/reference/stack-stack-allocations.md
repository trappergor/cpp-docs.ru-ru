---
title: -STACK (выделение памяти в стеке) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs:
- C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd61f1cd56043dd7e2a2234630d722850850735
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703343"
---
# <a name="stack-stack-allocations"></a>Параметр /STACK (выделение памяти в стеке)

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Примечания

Параметр/Stack задает размер стека в байтах. Используйте этот параметр только в том случае, если построить файл .exe.

`reserve` Значение указывает все выделение стека в виртуальной памяти. Для ARM x86 и x64 машины, размер стека по умолчанию — 1 МБ.

`commit` интерпретируется операционной системой. В Windows WindowsRT он указывает объем физической памяти для одновременного выделения. Выделенной виртуальной памяти резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда приложения требуется больше пространства стека, но увеличивает требования к памяти и, возможно, время запуска. Для ARM x86 и x64 машин фиксации по умолчанию равен 4 КБ.

Укажите `reserve` и `commit` значения в десятичном или нотации языка.

Другой способ задать размер стека — с помощью [STACKSIZE](../../build/reference/stacksize.md) инструкции в файл определения модуля (DEF). **STACKSIZE** переопределяет выделение стека (/ STACK), если они указаны одновременно. Можно изменить размер стека после построения с помощью файла .exe [EDITBIN](../../build/reference/editbin-reference.md) средство.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **системы** страницу свойств.

1. Измените одно из следующих свойств:

   - **Фиксируемый размер стека**

   - **Резервируемый размер стека**

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)