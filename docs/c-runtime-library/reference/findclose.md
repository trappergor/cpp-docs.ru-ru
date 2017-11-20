---
title: "_findclose | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _findclose
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs: C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8deae0204a9165ee9ab89036faab3b762c536349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="findclose"></a>_findclose
Закрывает указанный дескриптор поиска и освобождает связанные ресурсы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `handle`  
 Дескриптор поиска, возвращенный предыдущим вызовом `_findfirst`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха `_findclose` возвращает 0. В противном случае возвращается значение -1 и задает `errno` для `ENOENT`, может быть найден, указывающее, что больше нет сопоставления файлов.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_findclose`|\<io.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Системные вызовы](../../c-runtime-library/system-calls.md)   
 [Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)