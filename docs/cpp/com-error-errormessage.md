---
title: "_com_error::ErrorMessage | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorMessage"
  - "_com_error.ErrorMessage"
  - "ErrorMessage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorMessage - метод"
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::ErrorMessage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлекает строковое сообщение для `HRESULT`, хранящееся в объекте `_com_error`.  
  
## Синтаксис  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Возвращает строковое сообщение для `HRESULT`, записанное в объекте `_com_error`.  Если `HRESULT` сопоставлен 16\-битный код [wCode](../cpp/com-error-wcode.md), возвращается универсальное сообщение "`IDispatch error #<wCode>`".  Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`".  В зависимости от состояния макроса **\_UNICODE**, возвращается строка Юникода или многобайтовая строка.  
  
## Заметки  
 Извлекает соответствующий текст системного сообщения для `HRESULT`, записанный в объекте `_com_error`.  Для получения текста системного сообщения вызывается функция Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351).  Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)