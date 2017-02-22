---
title: "Пределы поля &quot;Путь&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_MAX_EXT"
  - "_MAX_DIR"
  - "_MAX_PATH"
  - "_MAX_FNAME"
  - "_MAX_DRIVE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MAX_DIR - константа"
  - "_MAX_DRIVE - константа"
  - "_MAX_EXT - константа"
  - "_MAX_FNAME - константа"
  - "_MAX_PATH - константа"
  - "MAX_DIR - константа"
  - "MAX_DRIVE - константа"
  - "MAX_EXT - константа"
  - "MAX_FNAME - константа"
  - "константы поля пути"
  - "пути, максимальный лимит"
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Пределы поля &quot;Путь&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
#include <stdlib.h>  
```  
  
## Заметки  
 Эти константы определяет максимальную длину для пути и для отдельных полей в пути.  
  
|Константа|Значение|  
|---------------|--------------|  
|`_MAX_DIR`|Максимальная длина компонента каталога|  
|`_MAX_DRIVE`|Максимальная длина компонента диска|  
|`_MAX_EXT`|Максимальная длина компонента расширения|  
|`_MAX_FNAME`|Максимальная длина компонента имени файла|  
|`_MAX_PATH`|Максимальная длина полного пути|  
  
> [!NOTE]
>  Среда выполнения языка C поддерживает длины пути до 32768 символов, но это зависит от операционной системы, в частности от файловой системы, поддерживать ли эти более длинные пути.  Общая длина полей не должна превышать `_MAX_PATH` для полной обратной совместимости с файловыми системами FAT32.  [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../Token/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] и файловая система NTFS Windows Vista поддерживают пути до 32768 символов в длину, но только при использовании API Юникода.  При использовании длинных путей следует начинать путь с символов \\\\?\\ и использовать версии функций среды выполнения языка С для Юникода.  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)