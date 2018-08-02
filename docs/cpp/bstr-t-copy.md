---
title: _bstr_t::Copy | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7032d9344ec9375059d5584d080854ffe5c775
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405344"
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Блок, относящийся только к системам Microsoft**  
  
 Создает копию инкапсулированного объекта `BSTR`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BSTR copy( bool fCopy = true ) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 *fCopy*  
 Если значение равно TRUE, **копирования** возвращает копию содержащегося `BSTR`, в противном случае **копирования** возвращает фактический объект BSTR.  
  
## <a name="remarks"></a>Примечания  
 Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.  
  
## <a name="example"></a>Пример  
  
```cpp 
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)