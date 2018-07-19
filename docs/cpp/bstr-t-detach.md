---
title: _bstr_t::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8b7bc86ae487843f925668bccfbfd8e67b8685
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940255"
---
# <a name="bstrtdetach"></a>_bstr_t::Detach
**Блок, относящийся только к системам Microsoft**  
  
 Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BSTR Detach( ) throw;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `BSTR` в оболочке `_bstr_t`.  
  
## <a name="example"></a>Пример  
 См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример с использованием `Detach`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)