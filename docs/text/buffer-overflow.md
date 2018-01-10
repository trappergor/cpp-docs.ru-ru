---
title: "Переполнение буфера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bfad181ee7c6b702af87bc8ff0a49ccfb42cb65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="buffer-overflow"></a>Переполнение буфера
Изменение размера знаков может вызвать проблемы при помещении в буфер символов. Рассмотрим следующий код, который копирует символы из строки, `sz`, в буфер, `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Вопрос: был ли последний скопированный байт старшим байтом? Следующее не решает проблему, так как существует потенциальная возможность переполнения буфера:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` Пытается выполнить вызов — копирование полного знака, указывающее, является ли оно 1 или 2 байта. Однако он не принимает во внимание, что последний скопированный знак может не поместиться в буфер при символ занимает 2 байта. Правильным решением является:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Этот код проверяет возможное переполнение буфера в цикле тесте с помощью `_mbclen` для тестирования размера текущего знака, на который указывает `sz`. Путем вызова `_mbsnbcpy` функции, замените код в `while` цикл с единой строки кода. Пример:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)