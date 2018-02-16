---
title: "_ltoa, _ltow | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ltoa
- _ltow
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
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25dc7c06f2e5eadacb568a096fda30f81a16570b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ltoa-ltow"></a>_ltoa, _ltow
Преобразует целое число типа long в строку. Существуют более безопасные версии этих функций; см. статью [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
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
 Функция `_ltoa` преобразует цифры `value` в строку знаков, завершающуюся значением NULL, и сохраняет результат (до 33 байт) в `str`. `radix` Аргумент задает основание системы счисления `value`, которое должно быть в диапазоне от 2-36. Если `radix` равно 10 и `value` имеет отрицательное значение, первым символом результирующей строки будет знак «минус» (-). `_ltow` — это версия с расширенными символами для `_ltoa`; второй аргумент и возвращаемое значение функции `_ltow` являются строками с расширенными символами. Каждая из этих функций является специфичной для систем Microsoft.  
  
> [!IMPORTANT]
>  Чтобы предотвратить переполнение буфера, убедитесь, что буфер `str` достаточно велик для хранения преобразованных цифр, а также конечного нуль-символа и символа знака.  
  
 В C++ эти функции имеют шаблонные перегрузки. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)