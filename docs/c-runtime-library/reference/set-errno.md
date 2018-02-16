---
title: "_set_errno | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_errno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_errno
- _set_errno
dev_langs:
- C++
helpviewer_keywords:
- errno global variable
- set_errno function
- _set_errno function
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f1f5a87ab9f40eb229d4ebb7c23d584a5347094
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="seterrno"></a>_set_errno
Задает значение глобальной переменной `errno`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _set_errno(   
   int value   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `value`  
 Новое значение `errno`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль при успешном завершении.  
  
## <a name="remarks"></a>Примечания  
 Возможные значения макроса определяются в Errno.h. Также см. раздел [Константы errno](../../c-runtime-library/errno-constants.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_set_errno.c  
#include <stdio.h>  
#include <errno.h>  
  
int main()  
{  
   _set_errno( EILSEQ );  
   perror( "Oops" );  
}  
```  
  
```Output  
Oops: Illegal byte sequence  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_set_errno`|\<stdlib.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [_get_errno](../../c-runtime-library/reference/get-errno.md)   
 [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)