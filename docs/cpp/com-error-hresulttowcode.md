---
title: _com_error::HRESULTToWCode | Документация Майкрософт
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
ms.openlocfilehash: dbcbd73f1a4a6d80ed30a5d70ca43d5fe45677f9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941721"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляется 16-разрядное в 32-разрядное значение HRESULT `wCode`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *hr*  
 32-разрядное значение HRESULT должны быть сопоставлены с 16-разрядное `wCode`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 16-разрядное `wCode` , полученного из 32-разрядное значение HRESULT.  
  
## <a name="remarks"></a>Примечания  
 См. в разделе [_com_error::WCode](../cpp/com-error-wcode.md) Дополнительные сведения.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [Класс _com_error](../cpp/com-error-class.md)