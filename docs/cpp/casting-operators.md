---
title: "Операторы приведения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a516297b687db349a6bcc867fc94dcd85118a8a5
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
