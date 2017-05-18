---
title: "_CrtIsValidHeapPointer | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtIsValidHeapPointer
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
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 12
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a046822352800d01fb16ef8ef992dde6eeaf2fc2
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer
Проверяет, находится ли заданный указатель в куче, выделенной определенной библиотекой среды выполнения C, но не обязательно библиотекой CRT вызывающей функции. В версиях CRT, выпущенных до выхода Visual Studio 2010, эта функция проверяла, находится ли заданный указатель в локальной куче (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `userData`  
 Указатель на начало выделенного блока памяти.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_CrtIsValidHeapPointer` возвращает значение TRUE, если заданный указатель находится в куче, общей для всех экземпляров библиотеки CRT. В версиях CRT, выпущенных до выхода Visual Studio 2010, эта функция возвращала значение TRUE, если указатель находился в локальной куче. В противном случае функция возвращает значение FALSE.  
  
## <a name="remarks"></a>Примечания  
 Использовать эту функцию не рекомендуется. Начиная с библиотеки CRT в Visual Studio 2010, все библиотеки CRT используют одну и ту же кучу операционной системы — *кучу процесса*. Функция `_CrtIsValidHeapPointer` сообщает, выделен ли указатель в кучу CRT, но не указывает, был ли он выделен библиотекой CRT вызывающей функции. Возьмем для примера блок, выделенный с помощью библиотеки CRT в составе Visual Studio 2010. Если функция `_CrtIsValidHeapPointer`, экспортированная с помощью библиотеки CRT в составе Visual Studio 2012, проверит указатель, то вернет значение TRUE. Необходимости в такой проверке больше нет. В версиях библиотеки CRT до Visual Studio 2010 эта функция используется для проверки наличия того или иного адреса памяти в локальной куче. Локальная куча обращается к куче, созданной и управляемой определенным экземпляром библиотеки среды выполнения C. Если библиотека динамической компоновки (DLL) содержит статическую ссылку на библиотеку среды выполнения, она имеет свой собственный экземпляр кучи среды выполнения, а значит и собственную кучу, не зависящую от локальной кучи приложения. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtIsValidHeapPointer` удаляются на этапе предварительной обработки.  
  
 Так как эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 Дополнительные сведения о том, как использовать `_CrtIsValidHeapPointer` с другими функциями и макросами отладки, см. в статье [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как проверить допустимость памяти, если используется библиотека среды выполнения C до Visual Studio 2010. Пример приведен для пользователей предыдущих версий библиотеки кодов CRT.  
  
```  
// crt_isvalid.c  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then tests the validity of this memory by calling   
 * _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
#define  TRUE   1  
#define  FALSE  0  
  
int main( void )  
{  
        char *my_pointer;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header information  
         */  
        my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,   
        _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
        // Ensure that the memory got allocated correctly  
        _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,   
        NULL, NULL, NULL );  
  
         // Test for read/write accessibility  
        if (_CrtIsValidPointer((const void *)my_pointer,   
        sizeof(char) * 10, TRUE))  
                printf("my_pointer has read and write accessibility.\n");  
        else  
                printf("my_pointer only has read access.\n");  
  
        // Make sure my_pointer is within the local heap  
        if (_CrtIsValidHeapPointer((const void *)my_pointer))  
                printf("my_pointer is within the local heap.\n");  
        else  
                printf("my_pointer is not located within the local"  
                       " heap.\n");  
  
        free(my_pointer);  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
