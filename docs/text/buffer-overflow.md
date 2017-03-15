---
title: "Переполнение буфера | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "переполнения буфера [C++]"
  - "буферы [C++], размер символов"
  - "MBCS [C++], переполнение буфера"
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Переполнение буфера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Изменение размера знаков может вызвать проблемы при их помещении в буфер.  Рассмотрим следующий код, в котором знаки копируются из строки `sz` в буфер `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Вопрос заключается в том, был ли последний скопированный байт ведущим байтом?  Нижеследующее не может решить проблему, так как существует потенциальная возможность переполнения буфера:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Вызовы `_mbccpy` вполне корректно пытается выполнить копирование полного знака, вне зависимости от того, занимает он 1 или 2 байта.  Однако при этом не учитывается, что последний скопированный знак может не поместиться в буфер при размере знака 2 байта.  Правильным решением является:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 С помощью этого кода тестируется возможное переполнение буфера при циклическом тесте с помощью `_mbclen` для тестирования размера текущего знака, на который указывает `sz`.  Вызовом функции `_mbsnbcpy` можно заменить код в цикле `while` одной строкой кода.  Примеры.  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## См. также  
 [Советы по программированию многобайтовой кодировки](../Topic/MBCS%20Programming%20Tips.md)