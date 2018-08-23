---
title: _variant_t::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42fc4bd5186ade5efaa9c4fa8e9f567f37509039
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572888"
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Блок, относящийся только к системам Microsoft**  
  
 Отключает инкапсулированный `VARIANT` из данного `_variant_t` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VARIANT Detach( );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Инкапсулированный `VARIANT`.  
  
## <a name="remarks"></a>Примечания  
 Извлекает и возвращает инкапсулированный `VARIANT`, а затем очищает данный `_variant_t` объекта без его удаления. Эта функция-член удаляет `VARIANT` из инкапсуляции и задает `VARTYPE` этого `_variant_t` объекта значение VT_EMPTY. Вы выпуске возвращаемого `VARIANT` путем вызова [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) функции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)