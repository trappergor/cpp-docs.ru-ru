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
ms.workload: cplusplus
ms.openlocfilehash: 331e41cd5f333a1f2c628d50e6c4a34a3bc9dd96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-double"></a>Тип double
Значения типа double с двойной точностью имеют размер 8 байт. Формат напоминает формат чисел с плавающей запятой, за исключением того, что он имеет 11-разрядную экспоненту (ее значение может превышать 1023) и 52-разрядную мантиссу, а также еще один старший разряд. Значения типа double в этом формате могут находиться в диапазоне примерно от 1,7E–308 до 1,7E+308.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Тип double содержит 64 разряда: 1 для знака, 11 для экспоненты и 52 для мантиссы. Он имеет диапазон +/–1,7E308 с точностью не менее 15 знаков.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)