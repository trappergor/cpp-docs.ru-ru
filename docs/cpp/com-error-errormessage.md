---
title: _com_error::ErrorMessage | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c16b8bb6859cd65b534d804764257b901050995b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411241"
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