---
title: "_callnewh | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _callnewh
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords: _callnewh
dev_langs: C++
helpviewer_keywords: _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86085472c63d2ad3fbc1cf53d893bd8da2f8c244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="callnewh"></a>_callnewh
Вызывает *новый обработчик*, установленный на данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
```  
  
#### <a name="parameters"></a>Параметры  
 `size`  
 Объем памяти, который [оператор new](../../cpp/new-operator-cpp.md) пытается выделить.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Ошибка: новый обработчик либо не установлен, либо не активен.|  
|1|Успешное завершение: новый обработчик установлен и активен. Выделение памяти можно повторить.|  
  
## <a name="exceptions"></a>Исключения  
 Эта функция вызывает [bad_alloc](../../standard-library/bad-alloc-class.md), если *новый обработчик* обнаружить не удается.  
  
## <a name="remarks"></a>Примечания  
 *Новый обработчик* вызывается, если [оператору new](../../cpp/new-operator-cpp.md) не удается успешно выделить память. После этого новый обработчик может инициировать соответствующее действие, например освобождение памяти для успешного выполнения последующих распределений.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|_callnewh|internal.h|  
  
## <a name="see-also"></a>См. также  
 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md)