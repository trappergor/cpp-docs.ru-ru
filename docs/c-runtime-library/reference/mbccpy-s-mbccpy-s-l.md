---
title: "_mbccpy_s, _mbccpy_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs: C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 942267c2632e6ffafec3d2fa9308bfb3db69aa87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l
Копирует один многобайтовый символ из одной строки в другую. Это версии функций [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `dest`  
 Место назначения копирования.  
  
 [in] `buffSizeInBytes`  
 Размер буфера назначения.  
  
 [выходной] `pCopied`  
 Заполняется числом скопированных байтов (1 или 2 в случае успешного выполнения). Если это значение не важно, передайте `NULL`.  
  
 [in] `src`  
 Многобайтовый символ для копирования.  
  
 [in] `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи. Если `src` или `dest` имеет значение `NULL`, а также если требуется скопировать больше `buffSizeinBytes` байтов в `dest`, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `EINVAL` и устанавливают для параметра `errno` значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_mbccpy_s` копирует один многобайтовый символ из `src` в `dest`. Если `src` не указывает старший байт многобайтового символа, как определяется неявным вызовом функции [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), копируется один байт, на который указывает `src`. Если `src` указывает на старший байт, однако следующий байт равен 0 (то есть является недопустимым), в `dest` копируется 0, `errno` получает значение `EILSEQ`, а функция возвращает `EILSEQ`.  
  
 Функция `_mbccpy_s` не добавляет завершающий нуль-символ. Тем не менее, если `src` указывает на нуль-символ, в `dest` копируется значение NULL (обычное однобайтовое копирование).  
  
 Значение `pCopied` заполняется числом скопированных байтов. В случае успешного выполнения операции возможны значения 1 и 2. Если передано значение `NULL`, этот параметр не учитывается.  
  
|`src`|копируется в `dest`|`pCopied`|Возвращаемое значение|  
|-----------|----------------------|---------------|------------------|  
|не старший байт|не старший байт|1|0|  
|0|0|1|0|  
|старший байт, за которым следует не 0|старший байт, за которым следует не 0|2|0|  
|старший байт, за которым следует 0|0|1|`EILSEQ`|  
  
 Обратите внимание, что вторая строка представляет собой особый случай первой. Также обратите внимание, что в этой таблице предполагается `buffSizeInBytes`  >=  `pCopied`.  
  
 Функция `_mbccpy_s` использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. Функция `_mbccpy_s_l` идентична функции `_mbccpy_s`, но в функции `_mbccpy_s_l` для любого поведения, зависящего от языкового стандарта, используется переданный в параметре языковой стандарт.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|Сопоставляется макросу или встраиваемой функции.|`_mbccpy_s`|Сопоставляется макросу или встраиваемой функции.|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h>|  
|`_mbccpy_s_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)