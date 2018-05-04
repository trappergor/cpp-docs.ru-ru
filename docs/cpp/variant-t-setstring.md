---
title: _variant_t::SetString | Документы Microsoft
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
ms.openlocfilehash: 76aaf29febd04f95efc0922e0d2680976e1e97da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Блок, относящийся только к системам Microsoft**  
  
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