---
title: "Расширенные символы | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab885d5d807fe81b3058d533a70cdbaa9e3e523a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wide-characters"></a>Расширенные символы
**ANSI 3.1.3.4** Значение целочисленной символьной константы, которая содержит более одного символа, или расширенной символьной константы, которая содержит более одного многобайтового символа  
  
 Обычная символьная константа, ab, имеет целочисленное значение (int)0x6162. Если размер составляет более одного байта, то ранее считанные байты сдвигаются влево на значение **CHAR_BIT**, а следующий байт сравнивается (при помощи оператора побитового ИЛИ) с младшими битами значения **CHAR_BIT**. Число байтов в многобайтовой символьной константе не может превышать (int) — 4 байта в коде для 32-разрядной системы.  
  
 Многобайтовая символьная константа считывается так же и преобразуется в расширенную символьную константу с помощью функции времени выполнения `mbtowc`. Если результат не является допустимой многобайтовой символьной константой, выводится ошибка. В любом случае число байтов, проверяемое функцией `mbtowc`, ограничено значением `MB_CUR_MAX`.  
  
## <a name="see-also"></a>См. также  
 [Символы](../c-language/characters.md)