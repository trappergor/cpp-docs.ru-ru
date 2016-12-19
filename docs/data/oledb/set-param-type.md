---
title: "SET_PARAM_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SET_PARAM_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SET_PARAM_TYPE - макрос"
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SET_PARAM_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает макросы `COLUMN_ENTRY`, которые следуют за входными, выходными или и входными, и выходными макросами `SET_PARAM_TYPE`.  
  
## Синтаксис  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### Параметры  
 `type`  
 \[входные данные\] Тип, задаваемый для параметра.  
  
## Заметки  
 Поставщики поддерживают только входные и выходные типы параметров, поддерживаемые в базовом источнике данных. Тип представляет собой сочетание одного или нескольких значений **DBPARAMIO** \(см. раздел [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочнике программиста OLE DB*\).  
  
-   **DBPARAMIO\_NOTPARAM** Метод доступа не имеет параметров. Как правило, для **eParamIO** это значение задается в методах доступа к строкам, чтобы напомнить пользователям, что параметры игнорируются.  
  
-   **DBPARAMIO\_INPUT** Входной параметр  
  
-   **DBPARAMIO\_OUTPUT** Выходной параметр  
  
-   **DBPARAMIO\_INPUT &#124; DBPARAMIO\_OUTPUT** Параметр является входным и выходным.  
  
## Пример  
 [!CODE [NVC_OLEDB_Consumer#18](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#18)]  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)