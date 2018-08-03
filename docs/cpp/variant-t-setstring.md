---
title: _variant_t::SetString | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 090fd7ed027738ebe7bc9276e3b3f124b9212c4a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463471"
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Блок, относящийся только к системам Microsoft**  
  
 Присваивает строку данному объекту `_variant_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void SetString(const char* pSrc);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pSrc*  
 Указатель на строку знаков.  
  
## <a name="remarks"></a>Примечания  
 Преобразует символьную строку ANSI в строку `BSTR` Юникода и присваивает ее данному объекту `_variant_t`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)