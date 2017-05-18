---
title: "_strinc, _wcsinc, _mbsinc, _mbsinc_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
dev_langs:
- C++
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3eca42c7ad0563ce573dbaa2a75dd85739c342f5
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l
Увеличивает строковый указатель на один символ.  
  
> [!IMPORTANT]
>  `_mbsinc` и `_mbsinc_l` нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_strinc(  
   const char *current,  
   _locale_t locale  
);  
wchar_t *_wcsinc(  
   const wchar_t *current,  
   _locale_t locale  
);  
unsigned char *_mbsinc(  
   const unsigned char *current   
);  
unsigned char *_mbsinc_l(  
   const unsigned char *current,  
   _locale_t locale  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `current`  
 Указатель символа.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм возвращает указатель на символ, который следует сразу за `current`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_mbsinc` возвращает указатель на первый байт многобайтового символа, который следует сразу за `current`. `_mbsinc` распознает последовательности многобайтовых символов согласно используемой в данный момент [многобайтовой кодовой странице](../../c-runtime-library/code-pages.md); функция `_mbsinc_l` идентична, за исключением того, что она использует переданный параметр языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Функция универсального текста `_tcsinc`, определенная в Tchar.h, сопоставляется с `_mbsinc`, если определен флаг `_MBCS`, или с `_wcsinc`, если определен флаг `_UNICODE`. В противном случае `_tcsinc` сопоставляется с `_strinc`. `_strinc` и `_wcsinc` — версии `_mbsinc` с однобайтовыми или расширенными символами. `_strinc` и `_wcsinc` предоставляются только для этого сопоставления и не должны использоваться иным образом. Дополнительные сведения см. в разделах [Использование универсальных текстовых сопоставлений](../../c-runtime-library/using-generic-text-mappings.md) и [Универсальные текстовые сопоставления](../../c-runtime-library/generic-text-mappings.md).  
  
 Если параметр `current` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `EINVAL` и задает для `errno` значение `EINVAL`.  
  
> [!IMPORTANT]
>  Эти функции могут быть подвержены угрозам переполнения буфера. Переполнение буфера можно использовать для атак на систему, поскольку оно может привести к несанкционированному повышению уровня привилегий. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_mbsinc`|\<mbstring.h>|  
|`_mbsinc_l`|\<mbstring.h>|  
|`_strinc`|\<tchar.h>|  
|`_wcsinc`|\<tchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [_strdec, _wcsdec, _mbsdec, _mbsdec_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [_strninc, _wcsninc, _mbsninc, _mbsninc_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)
