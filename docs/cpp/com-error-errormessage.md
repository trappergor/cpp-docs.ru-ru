---
title: _com_error::ErrorMessage | Документация Майкрософт
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
ms.openlocfilehash: 9367e92110ba7fb232e89b9d950e491e5e8da5c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407173"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Блок, относящийся только к системам Microsoft**  
  
 Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const TCHAR * ErrorMessage( ) const throw( );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает строковое сообщение для HRESULT записанного в `_com_error` объекта. Если значение HRESULT равно сопоставлен 16-битный [wCode](../cpp/com-error-wcode.md), универсальное сообщение "`IDispatch error #<wCode>`" возвращается. Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`". Возвращаемая строка является Юникода или многобайтовая строка, в зависимости от состояния макроса _UNICODE.  
  
## <a name="remarks"></a>Примечания  
 Извлекает соответствующий текст системного сообщения для HRESULT записанного в `_com_error` объекта. Текст системного сообщения получается путем вызова Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) функции. Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)