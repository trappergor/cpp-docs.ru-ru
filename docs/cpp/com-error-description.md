---
title: "_com_error::Description | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3ed306a8eba4e76c2eefc738b617117188e85c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comerrordescription"></a>_com_error::Description
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы **IErrorInfo::GetDescription** функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат **IErrorInfo::GetDescription** для **IErrorInfo** записанного в `_com_error` объекта. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если не **IErrorInfo** будет записан, возвращается пустая коллекция типа `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Вызовы **IErrorInfo::GetDescription** функции и извлекает **IErrorInfo** записанного в `_com_error` объекта. Любые сбои при вызове **IErrorInfo::GetDescription** метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)