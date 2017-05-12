---
title: "_recalloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _recalloc
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
- _recalloc
- recalloc
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ae78e17f66448de46e36ea7d6dc6e3121b306c68
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="recalloc"></a>_recalloc
Комбинация `realloc` и `calloc`. Перераспределяет массив в памяти и инициализирует его элементы значением 0.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на ранее выделенный блок памяти.  
  
 `num`  
 Число элементов.  
  
 `size`  
 Длина каждого элемента в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_recalloc` возвращает указатель `void` в перераспределенном (и, возможно, перемещенном) блоке памяти.  
  
 Если доступной памяти недостаточно, чтобы расширить блок до заданного размера, исходный блок останется без изменений и будет возвращено значение `NULL`.  
  
 Если запрошенный размер равен нулю, то блок, на который указывает `memblock`, освобождается; возвращается значение `NULL`, `memblock` по-прежнему указывает на освобожденный блок.  
  
 Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличный от `void`, используйте приведение типов для возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 Функция `_recalloc` изменяет размер выделенного блока памяти. Аргумент `memblock` указывает на начало блока памяти. Если `memblock` — `NULL`, `_recalloc` ведет себя так же, как [calloc](../../c-runtime-library/reference/calloc.md) и выделяет новый блок `num`  *  `size` байт. Каждый элемент инициализируется значением 0. Если параметр `memblock` не имеет значение `NULL`, он должен быть указателем, возвращенным предыдущим вызовом функции `calloc`, [malloc](../../c-runtime-library/reference/malloc.md) или [realloc](../../c-runtime-library/reference/realloc.md).  
  
 Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный функцией `_recalloc`, не обязательно будет указателем, переданным через аргумент `memblock`.  
  
 Функция `_recalloc` задает для параметра `errno` значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Функция `recalloc` вызывает функцию `realloc` для использования функции C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md), чтобы установить новый режим обработки. Новый режим обработки указывает, должна ли функция `realloc` при сбое вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). По умолчанию в случае, если выделить память не удается, `realloc` не вызывает новую подпрограмму обработчика. Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти функцией `_recalloc` функция `realloc` вызывала новую подпрограмму обработчика таким же образом, как это делает оператор `new` при сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ.  
  
 Когда приложение связано с отладочной версией библиотеки времени выполнения C `_recalloc` разрешается [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Функция `_recalloc` имеет метки `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h> и \<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Параметры ссылок](../../c-runtime-library/link-options.md)
