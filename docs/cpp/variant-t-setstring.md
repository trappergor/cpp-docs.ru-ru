---
title: "_variant_t::SetString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
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
ms.openlocfilehash: 0e3502a83b93e89744e280cf9c01aa2d08b09a7e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Блок, относящийся только к системам Майкрософт**  
  
 Присваивает строку данному объекту `_variant_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pSrc`  
 Указатель на строку знаков.  
  
## <a name="remarks"></a>Примечания  
 Преобразует символьную строку ANSI в строку `BSTR` Юникода и присваивает ее данному объекту `_variant_t`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)
