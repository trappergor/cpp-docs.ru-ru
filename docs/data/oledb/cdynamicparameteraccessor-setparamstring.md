---
title: "CDynamicParameterAccessor::SetParamString | Microsoft Docs"
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
  - "ATL.CDynamicParameterAccessor.SetParamString"
  - "ATL::CDynamicParameterAccessor::SetParamString"
  - "SetParamString"
  - "CDynamicParameterAccessor::SetParamString"
  - "CDynamicParameterAccessor.SetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamString - метод"
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает строковые данные указанного параметра, хранящиеся в буфере.  
  
## Синтаксис  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pString`  
 \[in\] указатель на различных данных ANSI \(**char**\) или юникода \(**WCHAR**\) указанного параметра.  В разделе `DBSTATUS` в oledb.h.  
  
 *status*  
 \[in\] состояние `DBSTATUS` указанного параметра.  Сведения о значениях `DBSTATUS` см. в разделе [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) справочника *программиста OLE* DB или поиск `DBSTATUS` в oledb.h.  
  
## Заметки  
 Возвращает **true** в успехе или **false** при сбое.  
  
 `SetParamString` возникнет ошибка при попытке задать строку, превышает максимальный размер, указанный для `pString`.  
  
 Используйте `SetParamString`, чтобы разместить данные по параметров строк в буфере.  Используйте [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) для задания nonstring данные параметры в буфере.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)