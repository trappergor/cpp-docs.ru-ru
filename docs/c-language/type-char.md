---
title: "Тип char | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1046de3ca21cecf99c070a24a041e5c627d2961
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="type-char"></a>Тип char
Тип `char` используется для хранения целочисленного значения члена представительной кодировки. Целочисленное значение — это код ASCII, соответствующий указанному символу.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Значения символов типа `unsigned char` находятся в диапазоне от 0 до 0xFF по шестнадцатеричной системе счисления. **signed char** имеет диапазон от 0x80 до 0x7F. Эти диапазоны преобразуются в диапазоны от 0 до 255 и от -128 до +127 по десятичной системе счисления соответственно. Параметр компилятора /J меняет используемый по умолчанию вариант: вместо **signed** устанавливается `unsigned`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)