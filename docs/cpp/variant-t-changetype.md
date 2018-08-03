---
title: _variant_t::ChangeType | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f3790f4cb357ed830ba2c61b3c2906356dc64da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465592"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Блок, относящийся только к системам Microsoft**  
  
 Изменяет тип `_variant_t` на указанный `VARTYPE`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *VarType*  
 `VARTYPE` Для данного `_variant_t` объекта.  
  
 *pSrc*  
 Указатель на объект `_variant_t`, который необходимо преобразовать. Если это значение равно NULL, преобразование осуществляется на месте.  
  
## <a name="remarks"></a>Примечания  
 Эта функция-член преобразует `_variant_t` объекта в указанный `VARTYPE`. Если *pSrc* имеет значение NULL, преобразование осуществляется на месте, в противном случае это `_variant_t` объект копируется из *pSrc* , а затем преобразуется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)