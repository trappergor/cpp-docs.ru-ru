---
title: "_RTC_SetErrorFuncW | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f586823ffcab1e8d602375c9d955c78ac64c043f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения (RTC).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `function`  
 Адрес функции, которая будет обрабатывать проверки на ошибки во время выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ранее определенная функция обработки ошибок или `NULL`, если нет ранее определенной функции.  
  
## <a name="remarks"></a>Примечания  
 В новом коде используйте только `_RTC_SetErrorFuncW`. `_RTC_SetErrorFunc` включена в библиотеку только для обеспечения обратной совместимости.  
  
 Обратный вызов `_RTC_SetErrorFuncW` применяется только к компоненту, с которым он был связан, но не глобально.  
  
 Убедитесь, что передаваемый в `_RTC_SetErrorFuncW` адрес относится к допустимой функции обработки ошибок.  
  
 Если ошибке назначен тип значение -1, с помощью [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), вызывается функция обработки ошибок.  
  
 Перед тем, как вы сможете вызвать эту функцию, необходимо сначала вызвать одну из функций инициализации проверки на ошибки во время выполнения. Для получения дополнительной информации см. [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
 **_RTC_error_fnW** определяется следующим образом:  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  *linenumber* **, const wchar_t \*** `moduleName` **, const wchar_t \*** *format* **, ...);**  
  
 Здесь:  
  
 `errorType`  
 Тип ошибки, указанной [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md).  
  
 *filename*  
 Исходный файл, где произошел сбой, или значение NULL, если информация об отладке недоступна.  
  
 *linenumber*  
 Строка *filename* , где произошел сбой, или 0, если информация об отладке недоступна.  
  
 `moduleName`  
 Библиотека DLL или имя исполняемого файла, где произошел сбой.  
  
 *format*  
 Строка в стиле printf для отображения сообщения об ошибке с использованием оставшихся параметров. Первый аргумент VA_ARGLIST — номер возникшей ошибки RTC.  
  
 Пример, в котором показано, как использовать **_RTC_error_fnW**, см. в разделе [Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/native-run-time-checks-customization).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)