---
title: "_set_error_mode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
dev_langs: C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7987686fb0b9faa03cf4d5e4795116e9f0a608bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="seterrormode"></a>_set_error_mode
Изменяет `__error_mode` для определения отличного от используемого по умолчанию местоположения, куда среда выполнения C записывает сообщение об ошибке для ошибок, которые могут вызвать завершение программы.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `modeval`  
 Назначение сообщений об ошибках.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает старое значение или -1, если возникла ошибка.  
  
## <a name="remarks"></a>Примечания  
 Управляет приемником потока ошибок, устанавливая значение `__error_mode`. Например, можно направить вывод в стандартную ошибку или использовать API `MessageBox`.  
  
 Параметру `modeval` может быть присвоено одно из следующих значений:  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|Приемник ошибок определяется значением `__app_type`.|  
|`_OUT_TO_STDERR`|Приемником ошибок является стандартная ошибка.|  
|`_OUT_TO_MSGBOX`|Приемником ошибок является окно сообщения.|  
|`_REPORT_ERRMODE`|Сообщает текущее значение `__error_mode`.|  
  
 При передаче функции значения, отличного от перечисленных, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, `_set_error_mode` задает для `errno` значение `EINVAL` и возвращает значение -1.  
  
 При использовании с [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) `_set_error_mode` отображает ставший причиной сбоя оператор в диалоговом окне и предоставляет возможность нажать кнопку `Ignore` для продолжения выполнения программы.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h>|  
  
## <a name="example"></a>Пример  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>См. также  
 [Макрос assert, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)