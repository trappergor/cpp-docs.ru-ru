---
title: "_get_osfhandle | Документы Майкрософт"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffc65e12c4a9023d0ef649bbf2cb5e8f7e76808
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="getosfhandle"></a>_get_osfhandle

Получает дескриптор файла операционной системы, связанный с указанным дескриптором файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
### <a name="parameters"></a>Параметры

*fd*  
Дескриптор существующего файла.  
  
## <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор файла операционной системы, если *fd* является допустимым. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает `INVALID_HANDLE_VALUE` (-1) и задает `errno` для `EBADF`, указывающее, неправильный дескриптор файла.  
  
## <a name="remarks"></a>Примечания

Чтобы закрыть файл, получаемой в результате которого дескриптор файла операционной системы (ОС) `_get_osfhandle`, вызовите [ \_закрыть](../../c-runtime-library/reference/close.md) на дескриптор файла *fd*. Не следует вызывать `CloseHandle` для возвращаемого значения функции. Принадлежит базовый дескриптор файла операционной системы *fd* дескриптор файла, а затем закрывается, когда `_close` будет вызван на *fd*. Если владельцем дескриптора файла `FILE *` поток, затем вызвать [fclose](../../c-runtime-library/reference/fclose-fcloseall.md) об этом `FILE *` поток закрывает дескриптор файла и базовый дескриптор файла операционной системы. В этом случае не следует вызывать `_close` на дескриптор файла.
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)   
[_close](../../c-runtime-library/reference/close.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
