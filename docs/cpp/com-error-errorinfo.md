---
title: "_com_error::ErrorInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorInfo
dev_langs: C++
helpviewer_keywords: ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3e968a3b9814aeec898d4e157781b58c40a87e25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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