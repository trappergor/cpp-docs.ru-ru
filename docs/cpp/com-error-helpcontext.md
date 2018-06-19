---
title: _com_error::HelpContext | Документы Microsoft
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
ms.openlocfilehash: 7123fcf5859ce3fc373b29b4cb3e7b32109b464e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410828"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы **IErrorInfo::GetHelpContext** функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат **IErrorInfo::GetHelpContext** для **IErrorInfo** записанного в `_com_error` объекта. Если не **IErrorInfo** объекта записан, возвращается нулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове **IErrorInfo::GetHelpContext** метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)