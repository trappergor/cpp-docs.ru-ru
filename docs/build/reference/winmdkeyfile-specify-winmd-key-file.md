---
title: "-WINMDKEYFILE (укажите файл ключей winmd) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.WINMDKeyFile
dev_langs: C++
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc6fa7ff554a15e2d9f13ebfa21e577581ddbad0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (укажите файл ключей winmd)
Указывает ключ или пару ключей для подписи файла метаданных среды выполнения Windows (.winmd).  
  
```  
/WINMDKEYFILE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Напоминает [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) параметра компоновщика, который применяется к winmd-файл.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **метаданных Windows** страницу свойств.  
  
4.  В **файл ключа метаданных Windows** введите расположение файла.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)