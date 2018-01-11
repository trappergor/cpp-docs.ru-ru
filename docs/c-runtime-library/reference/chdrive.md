---
title: "_chdrive | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chdrive
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
- chdrive
- _chdrive
dev_langs: C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7733a366ade87dd937eb20eab97a5258db8787a
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="chdrive"></a>_chdrive
Изменяет текущий рабочий диск.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `drive`  
 Целое число от 1 до 26, указывающее текущий рабочий диск (1 = A, 2 = B и т. д.).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ноль (0), если текущий рабочий диск был успешно изменен; в противном случае возвращается −1.  
  
## <a name="remarks"></a>Примечания  
 Если параметр `drive` находится в диапазоне от 1 до 26, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция **_chdrive** возвращает значение −1, параметр `errno` принимает значение `EACCES`, а параметр `_doserrno` — значение `ERROR_INVALID_DRIVE`.  
  
 Функция **_chdrive** не является потокобезопасной, так как зависит от не безопасной для потоков функции **SetCurrentDirectory**. Для безопасного использования функции **_chdrive** в многопоточном приложении необходимо обеспечить собственный механизм синхронизации потоков. Дополнительные сведения см. на сайте [Библиотека MSDN](http://go.microsoft.com/fwlink/p/?linkid=150542), выполнив поиск по запросу **SetCurrentDirectory**.  
  
 Функция **_chdrive** изменяет текущий рабочий диск, а функция **_chdir** — текущий рабочий каталог.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|**_chdrive**|\<direct.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. примеры использования функции [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)