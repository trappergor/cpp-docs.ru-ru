---
title: _com_error::HelpFile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1f02238d228b5de4302812bacf4f9ad5cf1300c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409791"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы **IErrorInfo::GetHelpFile** функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат **IErrorInfo::GetHelpFile** для **IErrorInfo** записанного в `_com_error` объекта. Результирующая строка BSTR инкапсулируется в объект `_bstr_t`. Если не **IErrorInfo** будет записан, возвращается пустая коллекция типа `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове **IErrorInfo::GetHelpFile** метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)