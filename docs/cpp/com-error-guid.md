---
title: _com_error::GUID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee1952e50251cfac7563357c7626ab8603589e4d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409695"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы **IErrorInfo::GetGUID** функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат **IErrorInfo::GetGUID** для **IErrorInfo** записанного в `_com_error` объекта. Если не **IErrorInfo** объекта записан, возвращается `GUID_NULL`.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове **IErrorInfo::GetGUID** метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)