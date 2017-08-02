---
title: "Преобразования из других типов | Документация Майкрософт"
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
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 9
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e4a0b8b8a377808a18cc106cd2edeef7ecde4abc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="conversions-from-other-types"></a>Преобразования из других типов
Поскольку значение `enum` по определению имеет тип `int`, преобразования в тип `enum` и обратно выполняются так же, как и для типа `int`. В компиляторе Microsoft C тип integer обозначает то же самое, что и **long**.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Преобразование между типами структуры и объединения не допускаются.  
  
 Любое значение можно преобразовать в тип `void`, но результат такого преобразования можно использовать только в контексте, в котором значение выражения отбрасывается, например в операторе выражения.  
  
 Тип `void` по определению не имеет значения. Поэтому его невозможно преобразовать ни в какой другой тип, а другие типы невозможно преобразовать в `void` путем присваивания. Однако значение можно явным образом преобразовать в тип `void`, как описано в статье [Преобразования с приведением типов](../c-language/type-cast-conversions.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Преобразования назначений](../c-language/assignment-conversions.md)
