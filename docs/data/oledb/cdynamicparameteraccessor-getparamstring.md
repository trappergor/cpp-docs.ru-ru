---
title: "CDynamicParameterAccessor::GetParamString | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamString"
  - "GetParamString"
  - "CDynamicParameterAccessor::GetParamString"
  - "ATL.CDynamicParameterAccessor.GetParamString"
  - "ATL::CDynamicParameterAccessor::GetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamString - метод"
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает строковые данные указанного параметра, хранящиеся в буфере.  
  
## Синтаксис  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `strOutput`  
 \[out\] строковых данных ANSI \(**CSimpleStringA**\) или юникода \(**CSimpleStringW**\) указанного параметра.  Необходимо передать параметр типа `CString`, например:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 \[out\] указатель на различных данных ANSI \(**char**\) или юникода \(**WCHAR**\) указанного параметра.  
  
 `pMaxLen`  
 \[out\] указатель на размер буфера заданного в `pBuffer` \(в символах, включая конечное значение NULL\).  
  
## Заметки  
 Возвращает **true** в успехе или **false** при сбое.  
  
 Если `pBuffer` NULL, то этот метод установит необходимый размер буфера в памяти указанную в `pMaxLen` и возвращенному **true** без копирования данных.  
  
 Этот метод завершится неудачей, если буфер `pBuffer` недостаточно велик, чтобы содержать строку целиком.  
  
 Используйте `GetParamString` получить сведения о параметр строки из буфера.  Используйте [GetParam](../Topic/CDynamicParameterAccessor::GetParam.md), чтобы получить nonstring данные параметры из буфера.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)