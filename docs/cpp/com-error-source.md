---
title: _com_error::Source | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f904fa11195c27f8e08856ef391d0ba8adbedece
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939681"
---
# <a name="comerrorsource"></a>_com_error::Source
**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию `IErrorInfo::GetSource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат `IErrorInfo::GetSource` для `IErrorInfo` записанного в `_com_error` объекта. Результирующая строка BSTR инкапсулируется в объект `_bstr_t`. Если не `IErrorInfo` будет записан, возвращается пустой `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Любые сбои при вызове `IErrorInfo::GetSource` метод игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)