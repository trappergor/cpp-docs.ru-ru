---
title: "fsetpos | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fsetpos
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: fsetpos
dev_langs: C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 504ab55aadc315dcf06c07a999f2a7d3dfca630b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fsetpos"></a>fsetpos
Задает индикатор позиции в потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
 `pos`  
 Хранилище индикатора позиции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха `fsetpos` возвращает 0. В случае сбоя функция возвращает ненулевое значение и присваивает `errno` одну из следующих констант манифеста, которые определяются в файле ERRNO.H: `EBADF` (файл недоступен, или объект, на который указывает `stream`, не является допустимой файловой структурой) или `EINVAL` (было передано недопустимое значение для `stream` или `pos`). Если передан недопустимый параметр, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 `fsetpos` Функция задает для индикатора позиции файла `stream` значению `pos`, который получается в предыдущем вызове `fgetpos` от `stream`. Функция очищает индикатор end of file и отменяет последствия [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) на `stream`. После вызова `fsetpos` следующая операция над `stream` может выполнять как ввод, так и вывод данных.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)