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
ms.openlocfilehash: 848709fa6cbbbfb4166750f86540de2433a73023
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404032"
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