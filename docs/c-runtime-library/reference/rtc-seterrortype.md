---
title: "_RTC_SetErrorType | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 78f056e65523a39477bf138e6bd1664e0945a899
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType
Связывает обнаруженную проверкой во время выполнения ошибку (RTC) с типом. Обработчик ошибок определяет способ вывода ошибок указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _RTC_SetErrorType(  
   _RTC_ErrorNumber errnum,  
   int ErrType   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *errnum*  
 Число от нуля до единицы и меньше значения, возвращаемого [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md).  
  
 *ErrType*  
 Значение, присваиваемое *errnum*. Например, можно использовать **_CRT_ERROR**. Если вы используете `_CrtDbgReport` в качестве обработчика ошибок, *ErrType* может быть только одним из символов, определенных в [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md). Если у вас есть собственный обработчик ошибок ([_RTC_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)), у вас может быть столько же *ErrType*, сколько *errnum*.  
  
 *ErrType* для _RTC_ERRTYPE_IGNORE имеет специальное значение для `_CrtSetReportMode`; ошибка игнорируется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение для типа ошибки `type`.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию для всех ошибок задается значение *ErrType* = 1, которое соответствует **_CRT_ERROR**. Дополнительные сведения о типах ошибок по умолчанию, таких как **_CRT_ERROR**, см. в статье об [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Перед тем, как вы сможете вызвать эту функцию, необходимо сначала вызвать одну из функций инициализации проверок на ошибки во время выполнения; см. статью [Использование проверок во время выполнения без библиотеки времени выполнения C](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)
