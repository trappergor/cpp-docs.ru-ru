---
title: "_com_error::Source | Microsoft Docs"
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
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Source - метод"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию **IErrorInfo::GetSource**.  
  
## Синтаксис  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## Возвращаемое значение  
 Возвращает результат функции **IErrorInfo::GetSource** для объекта **IErrorInfo**, записанного в объекте `_com_error`.  Результирующая строка BSTR инкапсулируется в объект `_bstr_t`.  Если объект **IErrorInfo** не записан, возвращается пустой объект `_bstr_t`.  
  
## Заметки  
 Любые сбои при вызове метода **IErrorInfo::GetSource** игнорируются.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)