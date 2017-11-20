---
title: "_fread_nolock_s2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fread_nolock_s
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
f1_keywords:
- _fread_nolock_s
- stdio/_fread_nolock_s
dev_langs: C++
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e53f57a042216b0c910a74b4cea7c34eb1b62011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="freadnolocks"></a>_fread_nolock_s
Читает данные из потока, не блокируя другие потоки. Это версия функции [fread_nolock](../../c-runtime-library/reference/fread-nolock.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t _fread_nolock_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t elementCount,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения данных.  
  
 `bufferSize`  
 Размер буфера назначения в байтах.  
  
 `elementSize`  
 Размер читаемого элемента в байтах.  
  
 `elementCount`  
 Максимальное число читаемых элементов.  
  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 См. раздел [fread_s](../../c-runtime-library/reference/fread-s.md).  
  
## <a name="remarks"></a>Примечания  
 Эта функция представляет собой неблокирующую версию функции `fread_s`. Она идентична функции `fread_s` , но не защищена от помех со стороны других потоков. Эта функция может выполняться быстрее, поскольку она не создает дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эту функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fread_nolock_s`|C: \<stdio.h>; C++: \<cstdio> или \<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)