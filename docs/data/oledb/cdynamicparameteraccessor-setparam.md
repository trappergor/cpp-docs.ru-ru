---
title: "CDynamicParameterAccessor::SetParam | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicParameterAccessor::SetParam"
  - "ATL::CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor.SetParam"
  - "ATL.CDynamicParameterAccessor.SetParam"
  - "SetParam"
  - "CDynamicParameterAccessor:SetParam"
  - "CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor::SetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParam - метод"
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::SetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает буфер с помощью параметра определенные данные \(не строки\).  
  
## Синтаксис  
  
```  
  
      template < class   
      ctype >  
bool SetParam(  
   DBORDINAL nParam,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
template < class ctype >  
bool SetParam(  
   TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
```  
  
#### Параметры  
 `ctype`  
 Шаблонные параметра, тип данных.  
  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Примеры.  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 \[in\] Имя параметра.  
  
 `pData`  
 \[in\] указатель на адрес памяти, содержащий данные для записи в буфер.  
  
 *status*  
 \[in\] состояние столбца `DBSTATUS`.  Сведения о значениях `DBSTATUS` см. в разделе [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) справочника *программиста OLE* DB или поиск `DBSTATUS` в oledb.h.  
  
## Возвращаемое значение  
 Возвращает **true** в успехе или **false** при сбое.  
  
 Используйте `SetParam` для задания nonstring данные параметры в буфере.  Используйте [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md), чтобы разместить данные по параметров строк в буфере.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)