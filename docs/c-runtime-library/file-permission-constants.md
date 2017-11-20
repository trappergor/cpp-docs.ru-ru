---
title: "Константы разрешений файлов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs: C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa42ebf645c737ffe2f5db9647a3ba3912669b27
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="file-permission-constants"></a>Константы разрешений файлов
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Одна из этих констант обязательна при указании `_O_CREAT` (`_open`, `_sopen`).  
  
 Аргумент `pmode` определяет настройки разрешений файла следующим образом.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_S_IREAD`|Разрешено чтение|  
|`_S_IWRITE`|Разрешена запись|  
|`_S_IREAD` &#124; `_S_IWRITE`|Разрешены чтение и запись|  
  
 При использовании в качестве аргумента `pmode` для функции `_umask` эта константа манифеста задает настройки разрешений следующим образом.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_S_IREAD`|Запись запрещена (файл доступен только для чтения)|  
|`_S_IWRITE`|Чтение запрещено (файл доступен только для записи)|  
|`_S_IREAD` &#124; `_S_IWRITE`|Чтение и запись запрещены|  
  
## <a name="see-also"></a>См. также  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [Стандартные типы](../c-runtime-library/standard-types.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)