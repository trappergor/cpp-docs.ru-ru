---
title: "_com_error::Description | Microsoft Docs"
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
  - "_com_error.Description"
  - "_com_error::Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод описания"
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Description
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию **IErrorInfo::GetDescription**.  
  
## Синтаксис  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## Возвращаемое значение  
 Возвращает результат функции **IErrorInfo::GetDescription** для объекта **IErrorInfo**, записанного в объекте `_com_error`.  Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`.  Если объект **IErrorInfo** не записан, возвращается пустой объект `_bstr_t`.  
  
## Заметки  
 Вызывает функцию **IErrorInfo::GetDescription** и возвращает функцию **IErrorInfo**, записанную в объект `_com_error`.  Любые сбои при вызове метода **IErrorInfo::GetDescription** игнорируются.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)