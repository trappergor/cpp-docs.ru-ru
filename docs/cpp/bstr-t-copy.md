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
ms.openlocfilehash: d23f204e7e8a545fbee7ab516495ed711d7984a9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944639"
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
 Если значение равно TRUE, `copy` возвращает копию содержащегося `BSTR`, в противном случае `copy` возвращает фактический объект BSTR.  
  
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