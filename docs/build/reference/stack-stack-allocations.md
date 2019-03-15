---
title: Параметр /STACK (выделение памяти в стеке)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
ms.openlocfilehash: 27de554e1933b2753f641be358461c8d7ff4fffa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813803"
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

Другой способ задать размер стека — с помощью [STACKSIZE](stacksize.md) инструкции в файл определения модуля (DEF). **STACKSIZE** переопределяет выделение стека (/ STACK), если они указаны одновременно. Можно изменить размер стека после построения с помощью файла .exe [EDITBIN](editbin-reference.md) средство.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **системы** страницу свойств.

1. Измените одно из следующих свойств:

   - **Фиксируемый размер стека**

   - **Резервируемый размер стека**

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.

## <a name="see-also"></a>См. также

[Справочник по MSVC компоновщика](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
