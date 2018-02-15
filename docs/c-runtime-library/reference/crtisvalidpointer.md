---
title: "_CrtIsValidPointer | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e81cd074c9bd69386b300d307525a76515e02522
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer
Проверяет, не равен ли указатель нулю. В версиях библиотеки времени выполнения языка C, выпущенных до выхода Visual Studio 2010, проверяет, является ли указанный диапазон памяти допустимым для чтения и записи (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 адрес  
 Указывает начало диапазона памяти для проверки.  
  
 `size`  
 Размер указанного диапазона памяти (в байтах).  
  
 access  
 Доступ на чтение или запись для определения диапазона памяти.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Оператор `_CrtIsValidPointer` возвращает значение TRUE, если указатель не равен нулю. В версиях библиотеки CRT, выпущенных до выхода Visual Studio 2010, возвращает значение TRUE, если диапазон памяти допустим для указанной операции или операций. В противном случае функция возвращает значение FALSE.  
  
## <a name="remarks"></a>Примечания  
 Начиная с версии библиотеки CRT в составе Visual Studio 2010, параметры размера и доступа не учитываются, а `_CrtIsValidPointer` следит только за тем, чтобы указанный адрес не был пустым. Поскольку этот тест легко выполняется вручную, не рекомендуем использовать данную функцию. В версиях, выпущенных до выхода Visual Studio 2010, эта функция проверяет допустимость диапазона памяти, начинающегося по адресу `address` и занимающего заданное параметром `size` количество байт, для указанной операции или операций доступа. Если для параметра `access` задано значение TRUE, диапазон памяти проверяется для обеих операций: чтения и записи. Если значение параметра `access` — FALSE, проверяется допустимость диапазона памяти только для чтения. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtIsValidPointer` удаляются на этапе предварительной обработки.  
  
 Так как эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если диапазон памяти недопустим для операций чтения и записи.  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 Дополнительные сведения о том, как использовать `_CrtIsValidPointer` с другими функциями и макросами отладки, см. в статье [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h>|  
  
 `_CrtIsValidPointer` является расширением Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример для раздела [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)