---
title: "Константы setvbuf | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs: C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bdb0fd3ad3811e756458090a963f78bd716a581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setvbuf-constants"></a>Константы setvbuf
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы представляют тип буфера для `setvbuf`.  
  
 Возможные значения определяются следующими константами манифеста:  
  
|Константа|Значение|  
|--------------|-------------|  
|`_IOFBF`|Полная буферизация. Используется буфер, указанный в вызове функции `setvbuf`, и его размер равен указанному в вызове функции `setvbuf`. Если указатель буфера имеет значение **NULL**, используется автоматически выделенный буфер указанного размера.|  
|`_IOLBF`|Эквивалентно `_IOFBF`.|  
|`_IONBF`|Буфер не используется, независимо от аргументов в вызове функции `setvbuf`.|  
  
## <a name="see-also"></a>См. также  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)