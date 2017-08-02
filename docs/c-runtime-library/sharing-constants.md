---
title: "Совместное использование констант | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f2cf723738fccb92421f88b6c08405083f08e0fb
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="sharing-constants"></a>Совместное использование констант
Константы для режимов общего доступа к файлам.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Аргумент *shflag* определяет режим общего доступа и состоит из одной или нескольких констант манифеста. Их можно использовать в сочетании с аргументами *oflag* (см. [Константы файлов](../c-runtime-library/file-constants.md)).  
  
 В следующей таблице перечислены константы и их смысловые значения:  
  
|Константа|Значение|  
|--------------|-------------|  
|`_SH_DENYRW`|Запрещает доступ к файлу для чтения и записи|  
|`_SH_DENYWR`|Запрещает доступ к файлу для записи|  
|`_SH_DENYRD`|Запрещает доступ к файлу для чтения|  
|`_SH_DENYNO`|Разрешает доступ для чтения и записи|  
|`_SH_SECURE`|Устанавливает безопасный режим (совместный доступ для чтения, монопольный доступ для записи)|  
  
## <a name="see-also"></a>См. также  
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)
