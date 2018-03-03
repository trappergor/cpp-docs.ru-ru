---
title: "_bstr_t::Copy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4bbc3c33488d2925c1a7f879adf50f015f79ec8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Блок, относящийся только к системам Microsoft**  
  
 Создает копию инкапсулированного объекта `BSTR`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `fCopy`  
 Если **true**, **копирования** возвращает копию содержащегося `BSTR`, в противном случае **копирования** возвращает фактический объект BSTR.  
  
## <a name="remarks"></a>Примечания  
 Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.  
  
## <a name="example"></a>Пример  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)