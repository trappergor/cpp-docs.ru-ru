---
title: "Класс CDynamicParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicParameterAccessor"
  - "ATL::CDynamicParameterAccessor"
  - "CDynamicParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CDynamicParameterAccessor"
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Класс CDynamicParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Аналогичен классу [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), однако получает сведения о задаваемых параметрах путем вызова интерфейса [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx).  
  
## Синтаксис  
  
```  
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Конструктор.|  
|[GetParam](../Topic/CDynamicParameterAccessor::GetParam.md)|Получает данные параметров из буфера.|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Получает число параметров в методе доступа.|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Определяет, является ли указанный параметр входным или выходным.|  
|[GetParamLength](../Topic/CDynamicParameterAccessor::GetParamLength.md)|Получает длину указанного параметра, сохраненного в буфере.|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Получает имя указанного параметра.|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Получает состояние указанного параметра, сохраненного в буфере.|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Получает строковые данные указанного параметра, сохраненного в буфере.|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Получает тип данных указанного параметра.|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Задает буфер, используя данные параметра.|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Задает длину указанного параметра, сохраненного в буфере.|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Задает состояние указанного параметра, сохраненного в буфере.|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Задает строковые данные указанного параметра, сохраненного в буфере.|  
  
## Заметки  
 Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.  
  
 Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера можно с помощью методов [GetParam](../Topic/CDynamicParameterAccessor::GetParam.md) и [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Пример, демонстрирующий использование этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров, см. в статье базы знаний Q058860, HOWTO: Execute Stored Procedure using CDynamicParameterAccessor \(Практическое руководство. Выполнение хранимой процедуры с помощью метода CDynamicParameterAccessor\). Статьи базы знаний доступны в документации по Visual Studio библиотеки MSDN или на веб\-сайте [http:\/\/support.microsoft.com\/](http://support.microsoft.com).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../Topic/CAccessor%20Class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)