---
title: Операторы приведения | Документы Microsoft
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf4204e55811cd33fa48e2b3a07d3058100729ac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411651"
---
# <a name="casting-operators"></a>Операторы приведения
Некоторые операторы приведения типа используются только в языке C++. Эти операторы позволяют устранить неоднозначность и возможности допустить ошибку, которые характеры для приведения типов в стиле языка C. Эти операторы перечислены ниже.  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md) используется для преобразования полиморфных типов.  
  
-   [static_cast](../cpp/static-cast-operator.md) используется для преобразования неполиморфных типов.  
  
-   [const_cast](../cpp/const-cast-operator.md) используется для удаления `const`, `volatile`, и `__unaligned` атрибуты.  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md) используется для простой повторной интерпретации разрядов.  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md) используется для создания проверяемых MSIL.  
  
 В операторах `const_cast` и `reinterpret_cast` сохраняется опасность допустить ошибку (как в операторах приведения типов в C), поэтому их следует использовать только в тех случаях, когда обойтись без них не удается. Однако они необходимы, чтобы полностью заменить приведения старого стиля.  
  
## <a name="see-also"></a>См. также  
 [Приведение](../cpp/casting.md)