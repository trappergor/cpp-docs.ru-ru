---
title: _com_error::Description | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4be038bff05ce7a37b09ec3b3c61572635747864
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939901"
---
# <a name="comerrordescription"></a>_com_error::Description
**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию `IErrorInfo::GetDescription`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат `IErrorInfo::GetDescription` для `IErrorInfo` записанного в `_com_error` объекта. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если не `IErrorInfo` будет записан, возвращается пустой `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Вызовы `IErrorInfo::GetDescription` и возвращает функцию `IErrorInfo` записанного в `_com_error` объекта. Любые сбои при вызове `IErrorInfo::GetDescription` метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)