---
title: "_set_abort_behavior | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
dev_langs: C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edf31ccddfb9ab2eaa6de226ff4ec7eb09869438
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setabortbehavior"></a>_set_abort_behavior
Указывает действие, выполняемое при аварийном завершении программы.  
  
> [!NOTE]
>  Не используйте функцию `abort` для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки. Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса не допускается в соответствии с [сертификационными требованиями к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889). Дополнительные сведения см. в разделе [Жизненный цикл приложений (приложения для Магазина Windows)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `flags`  
 Новое значение флагов `abort`.  
  
 [in] `mask`  
 Маска для битов флагов `abort`, которую требуется задать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Старое значение флагов.  
  
## <a name="remarks"></a>Примечания  
 Существует два флага `abort`: `_WRITE_ABORT_MSG` и `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG` определяет, будет ли выводиться полезное текстовое сообщение при аварийном завершении программы. Сообщение указывает на то, что приложение вызвало функцию `abort`. По умолчанию сообщение выводится. Если задано, то `_CALL_REPORTFAULT` указывает, что создан аварийный дамп памяти Watson и отчет при вызове функции `abort`. По умолчанию функция создания отчетов о аварийных дампах включена в неотладочных сборках.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_abort_behavior`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
```Output  
Suppressing the abort message. If successful, this message will be the only output.  
```  
  
## <a name="see-also"></a>См. также  
 [abort](../../c-runtime-library/reference/abort.md)