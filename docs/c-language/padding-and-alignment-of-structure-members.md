---
title: "Заполнение и выравнивание членов структур| Документация Майкрософт"
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
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1d2a2c895e636937781c6068e8f3c8816e8814a5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="padding-and-alignment-of-structure-members"></a>Заполнение и выравнивание членов структуры
**ANSI 3.5.2.1** Заполнение и выравнивание членов структур, а также выяснение, может ли битовое поле пересекать границу блоков хранения в памяти  
  
 Структурные элементы сохраняются последовательно, в порядке объявления: первый элемент имеет самый низкий адрес памяти, а последний — наивысший.  
  
 Каждый объект данных имеет требования-к-выравниванию. Требование выравнивания для всех данных, кроме структур, объединений и массивов, равно размеру объекта или текущему упаковочному размеру (задается меньшим из двух значений: параметр /Zp или директива #pragma `pack`). Для структур, объединений и массивов требование к выравниванию равно наибольшему требованию к выравниванию для их членов. Каждому объекту задается такое смещение, чтобы  
  
 *offset*  `%` *alignment-requirement* `==` 0  
  
 Смежные битовые поля упакованы в тот же одно-, двух- или четырехбайтовый модуль распределения, если целочисленные типы имеют тот же размер и если следующее битовое поле помещается в текущий блок распределения, не пересекая границ, установленных общими требованиями выравнивания битовых полей.  
  
## <a name="see-also"></a>См. также  
 [Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)
