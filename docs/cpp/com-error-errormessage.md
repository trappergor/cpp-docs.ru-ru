---
title: "_com_error::ErrorMessage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorMessage
dev_langs: C++
helpviewer_keywords: ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8690c23acf6e42d355cf122f59f54e19cc36d66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Блок, относящийся только к системам Microsoft**  
  
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