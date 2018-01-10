---
title: "_set_new_mode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_new_mode
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
f1_keywords:
- set_new_mode
- _set_new_mode
dev_langs: C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 31fb5217c70c41e633fffc69cd05624366fa29eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setnewmode"></a>_set_new_mode
Устанавливает нового режима обработчика для `malloc`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `newhandlermode`  
 Новый режим обработчика для `malloc`; допустимое значение — 0 или 1.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает предыдущий режим обработчика, заданный для `malloc`. Возвращаемое значение 1 указывает, что в случае сбоя процесса выделения памяти функция `malloc` ранее вызвала новую подпрограмму обработчика; возвращаемое значение 0 указывает, что функция не выполняет этого действия. Если `newhandlermode` аргумент не равен 0 или 1, возвращается значение -1.  
  
## <a name="remarks"></a>Примечания  
 Функция `_set_new_mode` C++ задает новый режим обработчика для [malloc](../../c-runtime-library/reference/malloc.md). Новый режим обработки указывает, должна ли функция `malloc` при сбое вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). По умолчанию в случае, если выделить память не удается, `malloc` не вызывает новую подпрограмму обработчика. Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти функцией `malloc` функция `malloc` вызывала новую подпрограмму обработчика таким же образом, как это делает оператор `new` при сбое по той же причине. Дополнительные сведения см. в разделе об операторах [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) *справочника по языку C++*. Чтобы переопределить значение по умолчанию, вызовите:  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или выполните компоновку с использованием Newmode.obj (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).  
  
 Эта функция проверяет свои параметры. Если значение `newhandlermode` отличается от 0 или 1, функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция **_**`set_new_mode` возвращает значение –1 и устанавливает для параметра `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)