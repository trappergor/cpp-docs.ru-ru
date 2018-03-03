---
title: "-STACK (выделение памяти в стеке) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b487ff830abd3dfa97a748c81d541cbd9fdd0b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stack-stack-allocations"></a>Параметр /STACK (выделение памяти в стеке)
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/Stack задает размер стека в байтах. Используйте этот параметр только в том случае, когда сборки файла .exe.  
  
 `reserve` Значение указывает все выделение стека в виртуальной памяти. Для ARM, x86 и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] машины, размер стека по умолчанию составляет 1 МБ.  
  
 `commit`интерпретируется операционной системой. В Windows WindowsRT он задает объем физической памяти для выделения одновременно. Выделенная виртуальная память резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда приложение требуется больший объем стека, но увеличивает требования к памяти и, возможно, время запуска. Для ARM, x86 и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] машины фиксации по умолчанию равен 4 КБ.  
  
 Укажите `reserve` и `commit` значений в десятичное или нотации языка.  
  
 Другой способ настройки размера стека — с [STACKSIZE](../../build/reference/stacksize.md) инструкции в файл определения модуля (DEF). **STACKSIZE** переопределяет выделение стека (/ STACK), если они указаны одновременно. Размер стека можно изменить после построения с помощью файла .exe [EDITBIN](../../build/reference/editbin-reference.md) средства.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **системы** страницу свойств.  
  
4.  Измените один из следующих свойств:  
  
    -   **Выделить память для стека**  
  
    -   **Резервируемый размер стека**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)