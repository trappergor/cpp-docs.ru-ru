---
title: _variant_t::ChangeType | Документы Microsoft
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
ms.openlocfilehash: 53fd73fc9606053dda6f8c143618373ad9bb7e4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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