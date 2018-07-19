---
title: -WINMDKEYCONTAINER (указать контейнер ключей) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e4f74eb249c2687716fedb43ccf0a37e35f7b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376615"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (указать контейнер ключей)
Указывает контейнер ключей для подписания файла метаданных Windows (.winmd).  
  
```  
/WINMDKEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Примечания  
 Напоминает [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) параметра компоновщика, который применяется в файл (с расширением winmd).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **метаданных Windows** страницу свойств.  
  
4.  В **контейнер ключа метаданных Windows** введите расположение.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)