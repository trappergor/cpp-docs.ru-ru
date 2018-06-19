---
title: _com_error::WCodeToHRESULT | Документы Microsoft
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
ms.openlocfilehash: 31b9df8305d0eea772979904f63847f6d6c2325a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413379"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляет 16-разрядный `wCode` с 32-разрядным `HRESULT`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `wCode`  
 16-разрядный `wCode`, который будет сопоставлен с 32-разрядным `HRESULT`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 32-разрядный `HRESULT`, с которым будет сопоставлен 16-разрядный `wCode`.  
  
## <a name="remarks"></a>Примечания  
 В разделе [WCode](../cpp/com-error-wcode.md) функции-члена.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [Класс _com_error](../cpp/com-error-class.md)