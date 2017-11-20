---
title: "Тип double | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aa4e81164a02774f7f9aa034f2c1a5492233600d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="type-double"></a>Тип double
Значения типа double с двойной точностью имеют размер 8 байт. Формат напоминает формат чисел с плавающей запятой, за исключением того, что он имеет 11-разрядную экспоненту (ее значение может превышать 1023) и 52-разрядную мантиссу, а также еще один старший разряд. Значения типа double в этом формате могут находиться в диапазоне примерно от 1,7E–308 до 1,7E+308.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Тип double содержит 64 разряда: 1 для знака, 11 для экспоненты и 52 для мантиссы. Он имеет диапазон +/–1,7E308 с точностью не менее 15 знаков.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)