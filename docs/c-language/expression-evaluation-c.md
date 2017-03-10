---
title: "Вычисление выражений (C) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 6
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ec5d4e82d9235f4ef2f83de535b38273c741d29a
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluation-c"></a>Вычисление выражений (C)
Выражения, включающие назначение, унарный инкремент, унарный декремент или вызов функции, могут случайно оказать воздействие на вычисление (побочные эффекты). При достижении точки последовательности вычисление всех элементов, расположенных до нее, включая все побочные эффекты, гарантированно завершается до начала вычисления любого элемента после точки последовательности.  
  
 Побочные эффекты — это изменения, вызванные вычислением выражения. Побочные эффекты возникают при изменении значения переменной в результате вычисления выражения. Все операции присваивания имеют побочные эффекты. Вызовы функций также могут иметь побочные эффекты, если при этом изменяется значение видимого снаружи элемента в результате явного назначения или косвенного назначения с помощью указателя.  
  
## <a name="see-also"></a>См. также  
 [Операнды и выражения](../c-language/operands-and-expressions.md)
