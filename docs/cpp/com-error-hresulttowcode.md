---
title: "_com_error::HRESULTToWCode | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dac335f3cc2ea26602a5f8a91a47db7d1ebe39b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Блок, относящийся только к системам Майкрософт**  
  
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