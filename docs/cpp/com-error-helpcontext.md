---
title: _com_error::HelpContext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e800bd3100fa0199534f3e9bdf6646aa0ffc6860
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940902"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию `IErrorInfo::GetHelpContext`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат `IErrorInfo::GetHelpContext` для `IErrorInfo` записанного в `_com_error` объекта. Если нет `IErrorInfo` объекта записан, возвращается нулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове `IErrorInfo::GetHelpContext` метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)