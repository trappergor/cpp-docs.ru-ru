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
- _com_error.Description
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0d91f6fded1fa1c4ea4d44cadd0d9285913b5f42
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comerrordescription"></a>_com_error::Description
**Блок, относящийся только к системам Майкрософт**  
  
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
