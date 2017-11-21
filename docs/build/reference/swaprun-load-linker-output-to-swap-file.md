---
title: "-SWAPRUN (загрузка выходных данных компоновщика в файл подкачки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs: C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f41a89e74ec2e9ed34e0add12717dd0c135ce723
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/SWAPRUN предписывает операционной системе сначала Копировать компоновщика выходные данные в файл подкачки, а затем запускать образ оттуда. Это средство Windows NT 4.0 (и более поздние версии).  
  
 Если задан параметр NET, операционная система сначала копирует двоичный образ из сети в файл подкачки и загрузит его оттуда. Этот параметр полезен для запуска приложений по сети. Когда задан компакт-ДИСК, операционная система копирует образ на съемном диске файл подкачки и их загрузка.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **системы** страницу свойств.  
  
4.  Измените один из следующих свойств:  
  
    -   **Поменять местами запуска с компакт-диска**  
  
    -   **Поменять местами запуска из сети**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)