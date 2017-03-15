---
title: "_com_error::HelpContext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::HelpContext"
  - "HelpContext"
  - "_com_error.HelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpContext - метод"
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HelpContext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию **IErrorInfo::GetHelpContext**.  
  
## Синтаксис  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Возвращает результат функции **IErrorInfo::GetHelpContext** для объекта **IErrorInfo**, записанного в объекте `_com_error`.  Если объект **IErrorInfo** не записан, возвращает результат 0.  
  
## Заметки  
 Любые сбои при вызове метода **IErrorInfo::GetHelpContext** игнорируются.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)