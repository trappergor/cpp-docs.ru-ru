---
title: "_set_new_mode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_new_mode
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
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 57a578f8accf7244d71c0d8791a6e898ead7d242
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

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
