---
title: _com_error::HRESULTToWCode | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e3955fcda665e08e5415652a1e8f1f232d0fe13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляет 32-разрядный `HRESULT` с 16-разрядным `wCode`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `hr`  
 32-разрядный `HRESULT` должен быть сопоставлен 16-разрядное `wCode`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 16-разрядное `wCode` , полученного из 32-разрядных `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 В разделе [_com_error::WCode](../cpp/com-error-wcode.md) для получения дополнительной информации.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [Класс _com_error](../cpp/com-error-class.md)