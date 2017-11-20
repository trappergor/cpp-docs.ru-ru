---
title: "Преобразования из других типов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed56c0c9ab3186200d3cbb47224dedc60adddb2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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