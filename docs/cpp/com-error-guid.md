---
title: "_com_error::GUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "GUID"
  - "_com_error.GUID"
  - "_com_error::GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID - метод"
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::GUID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию **IErrorInfo::GetGUID**.  
  
## Синтаксис  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Возвращает результат функции **IErrorInfo::GetGUID** для объекта **IErrorInfo**, записанный в объекте `_com_error`.  Если записанный объект **IErrorInfo** отсутствует, возвращается `GUID_NULL`.  
  
## Заметки  
 Любые сбои при вызове метода **IErrorInfo::GetGUID** игнорируются.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)