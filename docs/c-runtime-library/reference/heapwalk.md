---
title: "_heapwalk | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapwalk
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
- heapwalk
- _heapwalk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87ff27007734f84b93d0ecb36f637ae22f72098b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="heapwalk"></a>_heapwalk
Выполняет обход кучи и возвращает сведения о следующей записи.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows, за исключением отладочных сборок. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `entryinfo`  
 Буфер, который будет содержать данные кучи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_heapwalk` возвращает одну из следующих целочисленных констант манифеста, определенных в файле Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Начальные сведения о заголовке недопустимы или не найдены.  
  
 `_HEAPBADNODE`  
 Куча повреждена или обнаружен плохой узел.  
  
 `_HEAPBADPTR`  
 Поле `_pentry` структуры `_HEAPINFO` не содержит допустимый указатель на кучу или `entryinfo` — указатель NULL.  
  
 `_HEAPEND`  
 Успешно достигнут конец кучи.  
  
 `_HEAPEMPTY`  
 Куча еще не инициализирована.  
  
 `_HEAPOK`  
 Пока без ошибок; `entryinfo` обновляется информацией о следующей записи кучи.  
  
 Кроме того, при возникновении ошибки функция `_heapwalk` устанавливает для параметра `errno` значение `ENOSYS`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_heapwalk` помогает при отладке в программах проблем, связанных с кучей. Функция выполняет обход кучи, проходя по одной записи при каждом вызове, и возвращает указатель на структуру типа `_HEAPINFO`, содержащую сведения о следующей записи кучи. Тип `_HEAPINFO`, определенный в файле Malloc.h, содержит следующие элементы.  
  
 `int *_pentry`  
 Указатель записи кучи.  
  
 `size_t _size`  
 Размер записи кучи.  
  
 `int _useflag`  
 Флаг, указывающий, используется ли запись кучи.  
  
 Вызов функции `_heapwalk`, возвращающий `_HEAPOK`, сохраняет размер записи в поле `_size` и устанавливает в поле `_useflag` значение `_FREEENTRY` или `_USEDENTRY` (обе константы определены в файле Malloc.h). Для доступа к этой информации о первой записи в куче следует передать в функцию `_heapwalk` указатель на структуру `_HEAPINFO`, в которой член `_pentry` имеет значение `NULL`. Если операционная система не поддерживает функцию `_heapwalk` (например, Windows 98), эта функция возвращает `_HEAPEND` и устанавливает для параметра `errno` значение `ENOSYS`.  
  
 Эта функция проверяет свои параметры. Если параметр `entryinfo` является указателем NULL, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `_HEAPBADPTR`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_heapwalk`|\<malloc.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
```Output  
  USED block at 00310650 of size 0100  
  USED block at 00310758 of size 0800  
  USED block at 00310F60 of size 0080  
  FREE block at 00310FF0 of size 0398  
  USED block at 00311390 of size 000D  
  USED block at 003113A8 of size 00B4  
  USED block at 00311468 of size 0034  
  USED block at 003114A8 of size 0039  
...  
  USED block at 00312228 of size 0010  
  USED block at 00312240 of size 1000  
  FREE block at 00313250 of size 1DB0  
OK - end of heap  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)