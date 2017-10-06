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
caps.latest.revision: 6
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
ms.openlocfilehash: 535bc332a108cf50badca116c496661b7c257bf7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Блок, относящийся только к системам Майкрософт**  
  
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
