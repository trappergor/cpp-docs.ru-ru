---
title: _com_error::Error | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7ddaefcf3bd46bf40b03c03d2d1fb00cf8fbbb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408431"
---
# <a name="comerrorerror"></a>_com_error::Error
**Блок, относящийся только к системам Microsoft**  
  
 Возвращает значение HRESULT, переданный в конструктор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Error( ) const throw( );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Необработанный элемент HRESULT, переданный в конструктор.  
  
## <a name="remarks"></a>Примечания  
 Получает инкапсулированный элемент HRESULT в `_com_error` объекта.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)