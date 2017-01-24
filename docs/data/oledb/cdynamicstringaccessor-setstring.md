---
title: "CDynamicStringAccessor::SetString | Microsoft Docs"
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
  - "CDynamicStringAccessor::SetString"
  - "CDynamicStringAccessor.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString - метод"
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::SetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает указанные данные столбца в виде строки.  
  
## Синтаксис  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### Параметры  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Особое значение 0 ссылается на столбец закладки, если таковые имеются.  
  
 `pColumnName`  
 \[in\] указатель на символьной строки, содержащей имя столбца.  
  
 `data`  
 \[in\] указатель на различных данным, в конкретному столбцу.  
  
## Возвращаемое значение  
 Указатель на строковое значение в, чтобы задать определенный столбец.  Значение типа `BaseType`, которой будет `CHAR`  или `WCHAR`  в зависимости от того, указано `_UNICODE`  или нет.  
  
## Заметки  
 Вторая форма переопределения принимает имя столбца в качестве строки ANSI и третья форма переопределения принимают имя столбца как строки юникода.  
  
 Если `_SECURE_ATL` определяется наличие ненулевое значение, сбой среды выполнения утверждения создается, если строка `data` ввода превышает максимально позволяемая длина указанного столбца данных.  В противном случае входная строка будет усечена, если она превышает максимально позволяемая длина.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)