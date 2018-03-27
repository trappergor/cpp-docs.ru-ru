---
title: "_ultoa, _ultow | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ultoa
- _ultow
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ultot
- ultow
- _ultoa
- _ultow
- _ultot
dev_langs:
- C++
helpviewer_keywords:
- ultot function
- converting integers
- _ultot function
- ultow function
- integers, converting
- _ultow function
- _ultoa function
- converting numbers, to strings
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94073b947848199bdc093f959ddceadcb1835f16
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ultoa-ultow"></a>_ultoa, _ultow
Преобразуют целое число типа long без знака в строку. Существуют более безопасные версии этих функций; см. раздел [_ultoa_s, _ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `value`  
 Число, которое требуется преобразовать.  
  
 `str`  
 Результирующая строка.  
  
 `radix`  
 Основание системы счисления `value`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на `str`. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функция `_ultoa` преобразует `value` в строку знаков, завершающуюся нуль-символом, и сохраняет результат (до 33 байт) в `str`. Проверка на переполнение не выполняется. `radix` Определяет основание системы счисления `value`; `radix` должен находиться в диапазоне от 2-36. `_ultow` — это версия функции `_ultoa` для расширенных символов.  
  
> [!IMPORTANT]
>  Чтобы предотвратить переполнение буфера, убедитесь, что буфер `str` достаточно велик для хранения преобразованных цифр, а также конечного нуль-символа.  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_ultoa`|\<stdlib.h>|  
|`_ultow`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)