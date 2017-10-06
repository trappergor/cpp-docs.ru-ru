---
title: "_com_error::ErrorMessage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
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
ms.openlocfilehash: 01f244a07e46c70cbd4810af666f55dc899e5c3a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Блок, относящийся только к системам Майкрософт**  
  
 Извлекает строковое сообщение для `HRESULT`, хранящееся в объекте `_com_error`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает строковое сообщение для `HRESULT`, записанное в объекте `_com_error`. Если `HRESULT` будет сопоставлен 16-битный [wCode](../cpp/com-error-wcode.md), универсальное сообщение "`IDispatch error #<wCode>`" возвращается. Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`". Возвращаемая строка является Юникода или многобайтовая строка, в зависимости от состояния **_UNICODE** макрос.  
  
## <a name="remarks"></a>Примечания  
 Извлекает соответствующий текст системного сообщения для `HRESULT`, записанный в объекте `_com_error`. Текст системного сообщения получается путем вызова метода Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) функции. Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)
