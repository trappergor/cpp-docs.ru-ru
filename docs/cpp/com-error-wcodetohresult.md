---
title: "_com_error::WCodeToHRESULT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::WCodeToHRESULT
dev_langs: C++
helpviewer_keywords: WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 925e1f7a2675dc0aaed3a0cab064e01681de673c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Блок, относящийся только к системам Майкрософт**  
  
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