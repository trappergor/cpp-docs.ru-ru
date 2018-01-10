---
title: "_mbbtype, _mbbtype_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs: C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae66b1c0765f496dcfe460c4ea7ff4f84e9333ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l
Возвращает тип байта, основываясь на предыдущем байте.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемый символ.  
  
 `type`  
 Тип байта для проверки.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_mbbtype` возвращает тип байта в строке. Это решение контекстно зависимо — на это указывает значение параметра `type`, который определяет условие проверки управления. `type` — это тип предыдущего байта в строку. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.  
  
|Значение `type`|Функция `_mbbtype` проверяет|Возвращаемое значение|`c`|  
|---------------------|--------------------------|------------------|---------|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_SINGLE` (0)|Один байт (0x20 — 0x7E, 0xA1 - 0xDF)|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_LEAD` (1)|Старший байт многобайтового символа (0x81 - 0x9F, 0xE0 - 0xFC)|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_ILLEGAL`<br /><br /> ( -1)|Недопустимый символ (любое значение, кроме 0x20 — 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|  
|1|Допустимый младший байт|`_MBC_TRAIL` (2)|Конечный байт многобайтового символа (0x40 - 0x7E, 0x80 - 0xFC)|  
|1|Допустимый младший байт|`_MBC_ILLEGAL`<br /><br /> ( -1)|Недопустимый символ (любое значение, кроме 0x20 — 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|  
  
## <a name="remarks"></a>Примечания  
 Функция `_mbbtype` определяет тип байта в многобайтовом символе. Если параметр `type` имеет любым значение, кроме 1, `_mbbtype` проверяет допустимый одиночный байт или старший байт многобайтового символа. Если значение параметра `type` равно 1, `_mbbtype` проверяет допустимый младший байт многобайтового символа.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версия `_mbbtype` этой функции использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; версия `_mbbtype_l` работает аналогично, но использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 В более ранних версиях функция `_mbbtype` называлась `chkctype`. Для нового кода используйте вместо нее `_mbbtype`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* Для определения констант манифеста, которые используются в качестве возвращаемых значений.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)