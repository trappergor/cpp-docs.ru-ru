---
title: -HEAP (задание размера кучи) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs:
- C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f853b46c9a4cc2ec8f396be2b2f8355270ccf95
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702699"
---
# <a name="heap-set-heap-size"></a>/HEAP (Установка размера кучи)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Примечания

Параметр/Heap задает размер кучи в байтах. Этот параметр предназначен только для использования, при построении файла .exe.

*Зарезервировать* аргумент задает общее выделение кучи виртуальной памяти. Размер кучи по умолчанию составляет 1 МБ. Компоновщик Округляет указанное значение до ближайшего 4 байт.

Необязательный `commit` аргумент указывает объем физической памяти для одновременного выделения. Выделенной виртуальной памяти резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда требуется больше пространства кучи приложения, но увеличивает требования к памяти и, возможно, время запуска.

Укажите *зарезервировать* и `commit` значения в десятичном или нотации языка.

Эта функция также доступна через файл определения модуля с [HEAPSIZE](../../build/reference/heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Изменить **выделить память для кучи** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)