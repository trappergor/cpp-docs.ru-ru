---
title: _com_error::ErrorInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbc735dfae1b30209eccfd14f1170826fb07680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Блок, относящийся только к системам Microsoft**  
  
 Извлекает **IErrorInfo** объект, переданный в конструктор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Необработанный **IErrorInfo** элемент, переданный в конструктор.  
  
## <a name="remarks"></a>Примечания  
 Получает инкапсулированный **IErrorInfo** элемент `_com_error` объекта, или **NULL** Если **IErrorInfo** элемента записывается. Вызывающий объект должен вызвать **выпуска** в возвращаемом объекте после завершения его использования.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)