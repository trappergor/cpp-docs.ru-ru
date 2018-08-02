---
title: Операторы отношения _variant_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32f9a45fcfaaff02cfb7cf765857957f20c41ba1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463045"
---
# <a name="variantt-relational-operators"></a>Операторы отношения _variant_t
**Блок, относящийся только к системам Microsoft**  
  
 Сравнивает два объекта `_variant_t` и определяет, равны ли они.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool operator==(  
   const VARIANT& varSrc) const;  
bool operator==(  
   const VARIANT* pSrc) const;  
bool operator!=(  
   const VARIANT& varSrc) const;  
bool operator!=(  
   const VARIANT* pSrc) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект `VARIANT` для сравнения с `_variant_t` объекта.  
  
 *pSrc*  
 Указатель на `VARIANT` для сравнения с `_variant_t` объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** если содержит сравнение, **false** в противном случае.  
  
## <a name="remarks"></a>Примечания  
 Сравнивает `_variant_t` со `VARIANT`, проверки равенства или неравенства.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)