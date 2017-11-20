---
title: "Пределы поля \"Путь\" | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs: C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0adde41ca70fa5fdc457772f6023b02f9550e2ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="path-field-limits"></a>Пределы поля "Путь"
## <a name="syntax"></a>Синтаксис  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы определяют максимальную длину пути и отдельных полей в пути.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_MAX_DIR`|Максимальная длина компонента каталога|  
|`_MAX_DRIVE`|Максимальная длина компонента диска|  
|`_MAX_EXT`|Максимальная длина компонента расширения|  
|`_MAX_FNAME`|Максимальная длина компонента имени файла|  
|`_MAX_PATH`|Максимальная длина полного пути|  
  
> [!NOTE]
>  Среда выполнения языка C поддерживает длину пути до 32768 символов, но поддержка таких длинных путей зависит от операционной системы, а именно, от файловой системы. Для полной обратной совместимости с файловыми системами FAT32 общая длина полей не должна превышать `_MAX_PATH`. [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../atl/reference/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] и файловая система NTFS Windows Vista поддерживают пути длиной до 32768, но только при использовании API Юникода. Если вы используете длинные пути, указывайте в начале пути символы \\\\?\ и используйте версии для Юникода функций среды выполнения языка С.  
  
## <a name="see-also"></a>См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)