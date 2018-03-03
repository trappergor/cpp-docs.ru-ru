---
title: "_variant_t::ChangeType | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fb59090ebc4c6ff9120e813ae12a9defbe618b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Блок, относящийся только к системам Microsoft**  
  
 Изменяет тип `_variant_t` на указанный **VARTYPE**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `vartype`  
 **VARTYPE** для этого `_variant_t` объекта.  
  
 `pSrc`  
 Указатель на объект `_variant_t`, который необходимо преобразовать. Если это значение равно **NULL**, преобразование осуществляется на месте.  
  
## <a name="remarks"></a>Примечания  
 Эта функция-член преобразует `_variant_t` в указанный **VARTYPE**. Если `pSrc` — **NULL**, преобразование осуществляется на месте, в противном случае этот `_variant_t` объект копируется из `pSrc` , а затем преобразуется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)