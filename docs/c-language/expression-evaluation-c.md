---
title: "Вычисление выражений (C) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21b78b659b4d4cd8f3bb5db849b3c64a5f66f971
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluation-c"></a>Вычисление выражений (C)
Выражения, включающие назначение, унарный инкремент, унарный декремент или вызов функции, могут случайно оказать воздействие на вычисление (побочные эффекты). При достижении точки последовательности вычисление всех элементов, расположенных до нее, включая все побочные эффекты, гарантированно завершается до начала вычисления любого элемента после точки последовательности.  
  
 Побочные эффекты — это изменения, вызванные вычислением выражения. Побочные эффекты возникают при изменении значения переменной в результате вычисления выражения. Все операции присваивания имеют побочные эффекты. Вызовы функций также могут иметь побочные эффекты, если при этом изменяется значение видимого снаружи элемента в результате явного назначения или косвенного назначения с помощью указателя.  
  
## <a name="see-also"></a>См. также  
 [Операнды и выражения](../c-language/operands-and-expressions.md)