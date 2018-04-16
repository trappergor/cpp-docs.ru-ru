---
title: _umask_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 315473748d64e572c73746ce6f6fc97ccc912bb0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="umasks"></a>_umask_s
Задает маску разрешений файла по умолчанию. Версия функции [_umask](../../c-runtime-library/reference/umask.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `mode`  
 Параметр разрешения по умолчанию.  
  
 [выходной] `oldMode`  
 Прежнее значение параметра разрешения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает код ошибки, если `Mode` не указывает допустимый режим или указатель `pOldMode` имеет значение `NULL`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`mode`|`pOldMode`|**Возвращаемое значение**|**Содержимое** `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|any|`NULL`|`EINVAL`|не изменено|  
|недопустимый режим|any|`EINVAL`|не изменено|  
  
 Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция `_umask_s` возвращает значение `EINVAL` и устанавливает параметр `errno` в значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 `_umask_s` , Функция задает маску разрешений файла текущего процесса значение режима, указанного по `mode`. Маска разрешений файла изменяет параметр разрешения для новых файлов, созданных `_creat`, `_open` или `_sopen`. Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.  
  
 Целочисленное выражение `pmode` содержит одну или обе из следующих констант манифеста, определенных в файле SYS\STAT.H:  
  
 `_S_IWRITE`  
 Разрешена запись.  
  
 `_S_IREAD`  
 Разрешено чтение.  
  
 `_S_IREAD | _S_IWRITE`  
 Разрешены чтение и запись.  
  
 Если заданы обе константы, они соединяются с помощью битового оператора ИЛИ ( `|` ). Если аргумент `mode` имеет значение `_S_IREAD`, чтение запрещено (файл доступен только для записи). Если аргумент `mode` имеет значение `_S_IWRITE`, запись запрещена (файл доступен только для чтения). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, установка бита чтения с помощью `_umask_s` не влияет на режимы файла.  
  
 Если `pmode` не является комбинацией одной из констант манифеста и не включает дополнительный набор констант, функция будет просто игнорировать это.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_umask_s`|\<io.h> и \<sys/stat.h> и \<sys/types.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
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
 [_umask](../../c-runtime-library/reference/umask.md)