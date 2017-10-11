---
title: "_com_error::ErrorInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e80dafb5d1472ec28631b13ab05a0dea0b4de4ba
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Блок, относящийся только к системам Майкрософт**  
  
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
