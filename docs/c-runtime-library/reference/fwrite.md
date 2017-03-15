---
title: "fwrite | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fwrite
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d7c61e8d7b201b2ff5cc0c23378e545e41642445
ms.lasthandoff: 02/24/2017

---
# <a name="fwrite"></a>fwrite
Записывает данные в поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Указатель на записываемые данные.  
  
 `size`  
 Размер элемента, в байтах.  
  
 `count`  
 Максимальное число записываемых элементов.  
  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 `fwrite` возвращает число полных фактически записанных элементов, которое может быть меньше, чем `count`, если возникает ошибка. Кроме того, в случае возникновения ошибки невозможно определить индикатор положения файла. Если `stream` или `buffer` является указателем NULL или в режиме Юникода указывается нечетное число байт для записи, функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функции задает для `errno` значение `EINVAL` и возвращает 0.  
  
## <a name="remarks"></a>Примечания  
 Функция `fwrite` записывает до `count` элементов (каждый длиной `size`) из `buffer` в выходной `stream`. Указатель файла, связанный с `stream` (при наличии), возрастает на число фактически записанных байт. Если `stream` открыт в текстовом режиме, каждый перевод строки заменяется парой "возврат каретки — перевод строки". Замена не влияет на возвращаемое значение.  
  
 Если `stream` открыт в режиме преобразования Юникода (например, если `stream` открывается вызовом метода `fopen` и с помощью параметра режима, который включает `ccs=UNICODE`, `ccs=UTF-16LE` или `ccs=UTF-8`, или если режим изменен на режим преобразования Юникода с помощью `_setmode` и параметра режима, который включает `_O_WTEXT`, `_O_U16TEXT` или `_O_U8TEXT`), `buffer` интерпретируется как указатель на массив `wchar_t`, который содержит данные UTF-16. Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.  
  
 Поскольку эта функция блокирует вызывающий поток, она потокобезопасна. Сведения о неблокирующей версии см. в описании функции `_fwrite_nolock`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример для [fread](../../c-runtime-library/reference/fread.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::IO::FileStream::Write](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx)  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)
