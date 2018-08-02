---
title: _variant_t::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 567a3387e79244443b784549d6223a14f78103ce
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464688"
---
# <a name="varianttattach"></a>_variant_t::Attach
**Блок, относящийся только к системам Microsoft**  
  
 Присоединяет `VARIANT` в коллекцию **_variant_t** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach(VARIANT& varSrc);  
```  
  
#### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект `VARIANT` объекта должны быть присоединены к это **_variant_t** объекта.  
  
## <a name="remarks"></a>Примечания  
 Принимает владельца `VARIANT` , инкапсулируя его. Эта функция-член освобождает все существующие инкапсулированные объекты `VARIANT`, затем копирует переданный `VARIANT`и задает его `VARTYPE` значение VT_EMPTY для убедитесь, что его ресурсы можно освободить только **_variant_t** деструктор.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)