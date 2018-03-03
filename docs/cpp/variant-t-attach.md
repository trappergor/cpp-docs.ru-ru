---
title: "_variant_t::Attach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: effeaaaf3f8df9eb100d5e92e760eb439a865552
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="varianttattach"></a>_variant_t::Attach
**Блок, относящийся только к системам Microsoft**  
  
 Присоединяет **VARIANT** объекта в `_variant_t` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект **VARIANT** объекта для присоединения к этому `_variant_t` объекта.  
  
## <a name="remarks"></a>Примечания  
 Принимает право на владение **VARIANT** , инкапсулируя его. Эта функция-член освобождает все существующие инкапсулированные объекты **VARIANT**, затем копирует переданный **VARIANT**и задает его **VARTYPE** для `VT_EMPTY` для убедитесь, что его ресурсы можно освободить только `_variant_t` деструктор.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)