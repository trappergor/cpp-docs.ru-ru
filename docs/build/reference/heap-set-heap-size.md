---
title: -HEAP (Установка размера кучи) | Документы Microsoft
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
ms.openlocfilehash: 7b968b3c8e9063eea897c70d4ae2a62a9a232d6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="heap-set-heap-size"></a>/HEAP (Установка размера кучи)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/Heap задает размер кучи в байтах. Этот параметр используется только при построении файла .exe.  
  
 *Зарезервировать* аргумент задает общее выделение кучи в виртуальной памяти. Размер кучи по умолчанию составляет 1 МБ. Компоновщик Округляет указанное значение до ближайших 4 байт.  
  
 Необязательный `commit` аргумент задает объем физической памяти для выделения одновременно. Выделенная виртуальная память резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда требуется больше пространства кучи приложения, но увеличивает требования к памяти и, возможно, время запуска.  
  
 Укажите *зарезервировать* и `commit` значений в десятичное или нотации языка.  
  
 Эта функция также доступна через файл определения модуля с [HEAPSIZE](../../build/reference/heapsize.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **системы** страницу свойств.  
  
4.  Изменить **выделить память для кучи** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)