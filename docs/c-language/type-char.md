---
title: "Тип char | Документы Майкрософт"
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
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7bdb4b1632f3f3d2b8b0537992efe5c0aaf28e8d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="type-char"></a>Тип char
Тип `char` используется для хранения целочисленного значения члена представительной кодировки. Целочисленное значение — это код ASCII, соответствующий указанному символу.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Значения символов типа `unsigned char` находятся в диапазоне от 0 до 0xFF по шестнадцатеричной системе счисления. **signed char** имеет диапазон от 0x80 до 0x7F. Эти диапазоны преобразуются в диапазоны от 0 до 255 и от -128 до +127 по десятичной системе счисления соответственно. Параметр компилятора /J меняет используемый по умолчанию вариант: вместо **signed** устанавливается `unsigned`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)
