---
title: "_com_error::ErrorInfo | Microsoft Docs"
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
  - "_com_error::ErrorInfo"
  - "ErrorInfo"
  - "_com_error.ErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorInfo - метод"
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::ErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Получает объект **IErrorInfo**, переданный конструктору.  
  
## Синтаксис  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Необработанный элемент **IErrorInfo**, переданный конструктору.  
  
## Заметки  
 Получает элемент **IErrorInfo**, инкапсулированный в объекте `_com_error`, или значение **NULL**, если элемент **IErrorInfo** не записывался.  Завершив использование возвращенного объекта, вызывающий объект должен вызвать для него метод **Release**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)