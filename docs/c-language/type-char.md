---
title: Тип char | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b4db02292398da5c35f2894d4ce278cea88a584
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386833"
---
# <a name="type-char"></a>Тип char
Тип `char` используется для хранения целочисленного значения члена представительной кодировки. Целочисленное значение — это код ASCII, соответствующий указанному символу.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Значения символов типа `unsigned char` находятся в диапазоне от 0 до 0xFF по шестнадцатеричной системе счисления. **signed char** имеет диапазон от 0x80 до 0x7F. Эти диапазоны преобразуются в диапазоны от 0 до 255 и от -128 до +127 по десятичной системе счисления соответственно. Параметр компилятора /J меняет используемый по умолчанию вариант: вместо **signed** устанавливается `unsigned`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)