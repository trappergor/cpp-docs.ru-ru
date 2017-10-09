---
title: "btowc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- btowc
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
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 71af03a57886b150d6543e3aa11bfb0e05896890
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="btowc"></a>btowc
Определяет, представляет ли целое число допустимый однобайтовый символ в начальном состоянии сдвига.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемое целое число.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает представление символа в виде расширенного символа, если целое число представляет допустимый однобайтовый символ в начальном состоянии сдвига. Возвращает символ WEOF, если целое число является символом EOF или не является допустимым однобайтовым символом в начальном состоянии сдвига. Выходные данные этой функции зависят от текущего языкового стандарта `LC_TYPE`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`btowc`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)
