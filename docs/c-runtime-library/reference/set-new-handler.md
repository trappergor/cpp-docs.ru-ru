---
title: "_set_new_handler | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_new_handler
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
- _set_new_handler
- set_new_handler
dev_langs: C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ab5d0da21b7034d1a5ab336854b87ae2d2cc429
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setnewhandler"></a>_set_new_handler
Передает управление механизму обработки ошибок, если оператору `new` не удается выделить память.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pNewHandler`  
 Указатель на предоставленную приложением функцию обработки памяти. Аргумент 0 вызывает удаление нового обработчика.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущую функцию обработки исключений, зарегистрированную функцией `_set_new_handler`, чтобы предыдущую функцию можно было впоследствии восстановить. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция C++ `_set_new_handler` определяет функцию обработки исключений, которая получает управление, если оператор `new` не смог выделить память. Если оператор `new` завершается ошибкой, система времени выполнения автоматически вызывает функцию обработки исключений, которая была передана в качестве аргумента в функцию `_set_new_handler`. `_PNH`, определенный в New.h, представляет собой указатель на функцию, которая возвращает тип `int` и принимает аргумент типа `size_t`. Используйте `size_t` для определения объема выделяемого пространства.  
  
 Обработчик по умолчанию отсутствует.  
  
 `_set_new_handler` фактически является схемой сборки мусора. Система времени выполнения делает попытку выделения памяти каждый раз, когда пользовательская функция возвращает ненулевое значение, и завершается неудачей, если пользовательская функция возвращает 0.  
  
 Вхождение функции `_set_new_handler` в программе регистрирует в системе времени выполнения функцию обработчика исключения, указанную в списке аргументов:  
  
```  
#include <new.h>  
int handle_program_memory_depletion( size_t )  
{  
   // Your code  
}  
int main( void )  
{  
   _set_new_handler( handle_program_memory_depletion );  
   int *pi = new int[BIG_NUMBER];  
}  
```  
  
 Можно сохранить адрес функции, которая была передан последней в функцию `_set_new_handler`, и восстановить ее позже:  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 Функция [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) C++ задает новый режим обработчика для [malloc](../../c-runtime-library/reference/malloc.md). Новый режим обработки указывает, должна ли функция `malloc` при сбое вызывать новую подпрограмму обработчика, заданную функцией `_set_new_handler`. По умолчанию в случае, если выделить память не удается, `malloc` не вызывает новую подпрограмму обработчика. Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти функцией `malloc` функция `malloc` вызывала новую подпрограмму обработчика таким же образом, как это делает оператор `new` при сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите:  
  
```  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или выполните компоновку с использованием Newmode.obj.  
  
 Если определяемый пользователем `operator new` указан, новые функции обработчик не вызываются автоматически при сбое.  
  
 Дополнительные сведения см. в разделе [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) в *Справочнике по языку C++*.  
  
 Для всех динамически связываемых DLL и исполняемых файлов определен один обработчик `_set_new_handler`; даже при вызове `_set_new_handler` ваш обработчик может быть заменен другим или вы можете непроизвольно заменить обработчик, установленный другой DLL или другим исполняемым файлом.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_new_handler`|\<new.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 В этом примере если выделение памяти завершается сбоем, управление передается обработчику MyNewHandler. Аргумент, переданный обработчику MyNewHandler, представляет собой запрошенное количество байтов. Значение, возвращаемое из MyNewHandler, представляет собой флаг, указывающий, нужна ли повторная попытка выделения памяти: ненулевое значение указывает, что выделение должно быть повторено, нулевое значение указывает, что произошла ошибка выделения памяти.  
  
```  
// crt_set_new_handler.cpp  
// compile with: /c  
#include <stdio.h>  
#include <new.h>  
#define BIG_NUMBER 0x1fffffff  
  
int coalesced = 0;  
  
int CoalesceHeap()  
{  
   coalesced = 1;  // Flag RecurseAlloc to stop   
   // do some work to free memory  
   return 0;  
}  
// Define a function to be called if new fails to allocate memory.  
int MyNewHandler( size_t size )  
{  
   printf("Allocation failed. Coalescing heap.\n");  
  
   // Call a function to recover some heap space.  
   return CoalesceHeap();  
}  
  
int RecurseAlloc() {  
   int *pi = new int[BIG_NUMBER];  
   if (!coalesced)  
      RecurseAlloc();  
   return 0;  
}  
  
int main()  
{  
   // Set the failure handler for new to be MyNewHandler.  
   _set_new_handler( MyNewHandler );  
   RecurseAlloc();  
}  
```  
  
```Output  
Allocation failed. Coalescing heap.  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)