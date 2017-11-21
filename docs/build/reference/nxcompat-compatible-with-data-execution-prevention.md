---
title: "-NXCOMPAT (совместимо с предотвращением исполнения данных) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /NXCOMPAT
dev_langs: C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d97b1b84ef6894e4ec161dbcecef47f6b676af23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))
Указывает, что исполняемый файл был протестирован на совместимость с функцией предотвращения исполнения данных Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/NXCOMPAT[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию **/NXCOMPAT** включен.  
  
 **: No** можно использовать для явного указания исполняемый файл как несовместимый с предотвращением исполнения данных.  
  
 Дополнительные сведения о Предотвращение выполнения данных см. статьи:  
  
-   [Подробное описание функции предотвращения выполнения данных (DEP)](http://go.microsoft.com/fwlink/?LinkID=157771) в центр справки и поддержки веб-сайта  
  
-   [Предотвращение выполнения данных](http://go.microsoft.com/fwlink/?LinkID=157770) на сайте MSDN  
  
-   [Предотвращение выполнения данных (Windows Embedded)](http://go.microsoft.com/fwlink/?LinkID=157768) на сайте MSDN  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)