---
title: "_umask | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _umask
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
f1_keywords: _umask
dev_langs: C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8651fd1aa1400b366c6db369eff7bfde8751507
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="umask"></a>_umask
Задает маску разрешений файла по умолчанию. Существует более безопасная версия этой функции, см. раздел [_umask_s](../../c-runtime-library/reference/umask-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pmode`  
 Параметр разрешения по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_umask` возвращает предыдущее значение `pmode`. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 `_umask` , Функция задает маску разрешений файла текущего процесса значение режима, указанного по `pmode`. Маска разрешений файла изменяет параметр разрешения для новых файлов, созданных `_creat`, `_open` или `_sopen`. Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.  
  
 Целочисленное выражение `pmode` содержит одну или обе из следующих констант манифеста, определенных в файле SYS\STAT.H:  
  
 `_S_IWRITE`  
 Разрешена запись.  
  
 `_S_IREAD`  
 Разрешено чтение.  
  
 `_S_IREAD | _S_IWRITE`  
 Разрешены чтение и запись.  
  
 Если заданы обе константы, они соединяются с помощью битового оператора ИЛИ ( `|` ). Если аргумент `pmode` имеет значение `_S_IREAD`, чтение запрещено (файл доступен только для записи). Если аргумент `pmode` имеет значение `_S_IWRITE`, запись запрещена (файл доступен только для чтения). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, установка бита чтения с помощью `_umask` не влияет на режимы файла.  
  
 Если `pmode` не является комбинацией одной из констант манифеста и не включает дополнительный набор констант, функция будет просто игнорировать это.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_umask`|\<io.h>, \<sys/stat.h>, \<sys/types.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)