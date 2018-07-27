---
title: _com_error::WCodeToHRESULT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dce98775007360e3fdd4177141f7a550548d3679
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939199"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляет 16-разрядный *wCode* 32-разрядное значение HRESULT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *WCode*  
 16-разрядный *wCode* сопоставляться с 32-разрядное значение HRESULT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение HRESULT, сопоставленное с 16-разрядной *wCode*.  
  
## <a name="remarks"></a>Примечания  
 См. в разделе [WCode](../cpp/com-error-wcode.md) функция-член.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [Класс _com_error](../cpp/com-error-class.md)