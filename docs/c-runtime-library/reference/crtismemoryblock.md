---
title: "_CrtIsMemoryBlock | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e884526e45e4bb8fbf1070fca8fd740d692dc285
ms.lasthandoff: 02/24/2017

---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
Проверяет, находится ли указанный блок памяти в локальной куче и имеет ли он действительный идентификатор типа блока отладочной кучи (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `userData`  
 Указатель на начало блока памяти, требующего проверки.  
  
 [in] `size`  
 Размер указанного блока в байтах.  
  
 [выходной] `requestNumber`  
 Указатель на номер выделения блока или `NULL`.  
  
 [выходной] `filename`  
 Указатель на имя исходного файла, который запрашивает блок или `NULL`.  
  
 [выходной] `linenumber`  
 Указатель на номер строки в исходном файле или `NULL`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_CrtIsMemoryBlock` возвращает `TRUE`, если указанный блок памяти находится в локальной куче и имеет допустимый идентификатор типа блока отладочной кучи; в противном случае функция возвращает `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtIsMemoryBlock` проверяет, находится ли указанный блок памяти в локальной куче и имеет ли он допустимый идентификатор типа блока. Эту функцию можно также использовать для получения порядкового номера распределения объекта, а также имени или номера строки исходного файла, содержащего исходный запрос на выделение блока памяти. Передача непустых значений параметров `requestNumber`, `filename` или `linenumber` заставляет `_CrtIsMemoryBlock` присваивать этим параметрам значения из заголовка отладки блока памяти, если блок находится в локальной куче. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtIsMemoryBlock` удаляются на этапе предварительной обработки.  
  
 Если `_CrtIsMemoryBlock` завершается ошибкой, возвращается `FALSE`, а выходным параметрам присваиваются значения по умолчанию: `requestNumber` и `lineNumber` принимают значение 0, а `filename` — значение `NULL`.  
  
 Так как эта функция возвращает значение `TRUE` или `FALSE`, ее можно передать в один из макросов [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Дополнительные сведения о том, как использовать `_CrtIsMemoryBlock` с другими функциями и макросами отладки, см. в статье [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример для раздела [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
