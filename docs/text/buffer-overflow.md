---
title: Переполнение буфера | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11a3da883dae4d292a55eb2537fd98609404b5a9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609516"
---
# <a name="buffer-overflow"></a>Переполнение буфера
Изменение размера знаков может вызвать проблемы при переводе символов в буфер. Рассмотрим следующий код, который копирует знаки из строки, `sz`, в буфер, `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Вопрос: был последний байт старшим байтом? Следующее не решит проблему, так как существует потенциальная возможность переполнения буфера:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` Пытается выполнить вызов — копирование полного знака, будь то 1 или 2 байта. Но он не принимает во внимание, что последний скопированный знак может не поместиться в буфер при символ занимает 2 байта. Правильным решением является:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Этот код проверяет возможное переполнение буфера в цикле тестирования, с помощью `_mbclen` для тестирования размера текущего знака, на которые указывают `sz`. С помощью вызова `_mbsnbcpy` функции, вы можете заменить код в **хотя** цикла с помощью одной строки кода. Пример:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)