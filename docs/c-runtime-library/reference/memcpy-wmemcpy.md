---
title: "memcpy, wmemcpy | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy
- wmemcpy
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
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
dev_langs: C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 312e4a63803f3661799c6ad832fdfee22af876c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy
Копирует байты между буферами. Существуют более безопасные версии этих функций; см. раздел [memcpy_s, wmemcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dest`  
 Новый буфер.  
  
 `src`  
 Буфер, из которого происходит копирование.  
  
 `count`  
 Число копируемых символов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `dest`.  
  
## <a name="remarks"></a>Примечания  
 `memcpy` копирует `count` байт из `src` в `dest`; `wmemcpy` копирует `count` расширенных символов (двухбайтовых). При перекрытии исходного и конечного буферов поведение `memcpy` не определено. Используйте `memmove` для обработки перекрывающихся областей.  
  
> [!IMPORTANT]
>  Убедитесь в том, что буфер назначения равен или превосходит по размеру исходный буфер. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!IMPORTANT]
>  Так как множество выявленных случаев переполнения буфера, которые могут привести к нарушениям безопасности, было связано с ненадлежащим использованием `memcpy`, эта функция была включена в список "запрещенных" в рамках программы Security Development Lifecycle (SDL).  Вы можете заметить, что некоторые библиотечные классы VC++ по-прежнему используют `memcpy`.  Более того, можно заметить, что оптимизирующий компилятор VC++ иногда также вызывает функцию `memcpy`.  Язык Visual C++ разрабатывался в соответствии с требованиями SDL, поэтому использование этой запрещенной функции тщательно анализировалось.  В случае использования в библиотеке вызовы были тщательно изучены на предмет того, не могут ли они вызвать переполнение буфера.  В случае с компилятором некоторые шаблоны кода были признаны идентичными шаблону `memcpy` и поэтому заменены на вызов функции.  В таких случаях использование функции `memcpy` не менее безопасно, чем использование исходных инструкций, поэтому вызов функции `memcpy`, оптимизированной в плане производительности, является более предпочтительным.  Точно так же, как использование "безопасных" функций CRT не гарантирует безопасности, использование "запрещенных" функций не обязательно приводит к опасным ситуациям (они просто требуют более внимательного подхода к обеспечению безопасности).  
>   
>  Так как использование функции `memcpy` в компиляторе VC++ и библиотеках было тщательно проанализировано, ее вызовы разрешены в коде, который в остальном соответствует процессу SDL.  Вызовы `memcpy` в исходном коде приложений соответствуют процессу SDL, только если они были проверены специалистами по безопасности.  
  
 Функции `memcpy` и `wmemcpy` будут выведены из употребления, только если перед оператором включения определена константа `_CRT_SECURE_DEPRECATE_MEMORY`, показывающая, что эти функции должны быть выведены из употребления, как в примере ниже.  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 или  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`memcpy`|\<memory.h> или \<string.h>|  
|`wmemcpy`|\<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Пример использования `memcpy` см. в разделе [memmove](../../c-runtime-library/reference/memmove-wmemmove.md).  
  
## <a name="see-also"></a>См. также  
 [Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)