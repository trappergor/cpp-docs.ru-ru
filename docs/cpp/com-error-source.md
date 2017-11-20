---
title: "_com_error::Source | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Source
dev_langs: C++
helpviewer_keywords: Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01f63158f2406505e833ab58dcb53e099c3348f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorsource"></a>_com_error::Source
**Блок, относящийся только к системам Майкрософт**  
  
 Вызовы **IErrorInfo::GetSource** функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат **IErrorInfo::GetSource** для **IErrorInfo** записанного в `_com_error` объекта. Результирующая строка BSTR инкапсулируется в объект `_bstr_t`. Если не **IErrorInfo** будет записан, возвращается пустая коллекция типа `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове **IErrorInfo::GetSource** метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)