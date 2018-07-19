---
title: _com_error::GUID | Документация Майкрософт
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
ms.openlocfilehash: e324a84a16874a7e33f8687943b1302fbdd73a7a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939030"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию `IErrorInfo::GetGUID`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат `IErrorInfo::GetGUID` для `IErrorInfo` записанного в `_com_error` объекта. Если нет `IErrorInfo` объекта записывается, то возвращается значение GUID_NULL.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове `IErrorInfo::GetGUID` метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)