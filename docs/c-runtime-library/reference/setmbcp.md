---
title: "_setmbcp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs: C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b09953ffdb1523078f31cad08d53253b9d79892
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setmbcp"></a>_setmbcp
Задает новую многобайтовую кодовую страницу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `codepage`  
 Новая кодовая страница для независимых от языкового стандарта многобайтовых подпрограмм.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0, если кодовая страница задана успешно. Если указано недопустимое значение кодовой страницы для `codepage`, возвращает -1 и кодовой страницы не изменяется. Устанавливает параметр `errno` в `EINVAL`, если происходит сбой выделения памяти.  
  
## <a name="remarks"></a>Примечания  
 Функция `_setmbcp` задает новую многобайтовую кодовую страницу. По умолчанию система времени выполнения автоматически устанавливает в качестве многобайтовой кодовой страницы кодовую страницу ANSI, используемую в системе по умолчанию. Заданная многобайтовая кодовая страница влияет на все не зависящие от языкового стандарта подпрограммы. Однако можно дать `_setmbcp` указание использовать кодовую страницу, определенную для текущего языкового стандарта (см. следующий список констант манифеста и соответствующих результатов поведения). Список подпрограмм, которые зависят от кодовой страницей языкового стандарта, а не от многобайтовой кодовой страницы, см. в разделе [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 Многобайтовая кодовая страница также влияет на обработку многобайтовых символов следующими подпрограммами библиотеки времени выполнения:  
  
||||  
|-|-|-|  
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 Кроме того, все подпрограммы библиотеки времени выполнения, которые получают в качестве параметров многобайтовые аргументы программы `argv` или `envp` (например, семейства `_exec` и `_spawn`), обрабатывают эти строки в соответствии с многобайтовой кодовой страницей. Следовательно, вызов функции `_setmbcp`, изменяющий многобайтовую кодовую страницу, влияет и на эти подпрограммы.  
  
 Для аргумента `codepage` может быть установлено одно из следующих значений:  
  
-   `_MB_CP_ANSI` Используется кодовая страница ANSI, полученная от операционной системы при запуске программы.  
  
-   `_MB_CP_LOCALE` Используется кодовая страница текущего языкового стандарта, полученная из предыдущего вызова [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   `_MB_CP_OEM` Используется кодовая страница OEM, полученная от операционной системы при запуске программы.  
  
-   `_MB_CP_SBCS` Используется однобайтовая кодовая страница. Если кодовая страница установлена в `_MB_CP_SBCS`, подпрограммы, подобные [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), всегда возвращают значение false.  
  
-   Любая другая допустимая кодовая страница, независимо от того, является ли значение ANSI, OEM или другой поддерживаемой операционной системой кодовой страницей (за исключением UTF-7 и UTF-8, которые не поддерживаются).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)