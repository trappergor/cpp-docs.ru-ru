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
- Copy method
- BSTR object, copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
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
ms.openlocfilehash: 25167305ae817ebd9d979c0145934996bbbfcddc
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Блок, относящийся только к системам Майкрософт**  
  
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
