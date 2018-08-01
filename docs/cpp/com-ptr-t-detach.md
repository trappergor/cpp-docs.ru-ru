---
title: _com_ptr_t::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf38e433f7042707b502a4cba2088db9412adb29
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405838"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Блок, относящийся только к системам Microsoft**  
  
 Извлекает и возвращает инкапсулированный указатель на интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Interface* Detach( ) throw( );  
```  
  
## <a name="remarks"></a>Примечания  
 Извлекает и возвращает инкапсулированный указатель на интерфейс и затем очищает область хранения инкапсулированного указателя в значение NULL. Поэтому указатель на интерфейс удаляется из инкапсуляции. Это следует вызвать метод `Release` на возвращаемый указатель интерфейса.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)