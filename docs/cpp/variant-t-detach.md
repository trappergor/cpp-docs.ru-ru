---
title: "_variant_t::Detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
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
ms.openlocfilehash: 402d8bfeb6aea45460124bdeaaa8b3ee485df622
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="varianttdetach"></a>_variant_t::Detach
**Блок, относящийся только к системам Майкрософт**  
  
 Отключает инкапсулированный **VARIANT** объекта из этого `_variant_t` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Инкапсулированный **VARIANT**.  
  
## <a name="remarks"></a>Примечания  
 Извлекает и возвращает инкапсулированный **VARIANT**, а затем очищает данный `_variant_t` объект без его удаления. Эта функция-член удаляет **VARIANT** из инкапсуляции и задает **VARTYPE** этого `_variant_t` объект `VT_EMPTY`. Можно освободить возвращаемый **VARIANT** путем вызова [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) функции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)
