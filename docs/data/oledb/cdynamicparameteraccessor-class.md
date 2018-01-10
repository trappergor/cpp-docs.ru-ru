---
title: "Класс CDynamicParameterAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs: C++
helpviewer_keywords: CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b0c2590866db418f1652ebd1a46c0465ccb99086
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessor-class"></a>Класс CDynamicParameterAccessor
Аналогичен классу [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , однако получает сведения о задаваемых параметрах путем вызова интерфейса [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Конструктор.|  
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|Получает данные параметров из буфера.|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Получает число параметров в методе доступа.|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Определяет, является ли указанный параметр входным или выходным.|  
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|Получает длину указанного параметра, сохраненного в буфере.|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Получает имя указанного параметра.|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Получает состояние указанного параметра, сохраненного в буфере.|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Получает строковые данные указанного параметра, сохраненного в буфере.|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Получает тип данных указанного параметра.|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Задает буфер, используя данные параметра.|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Задает длину указанного параметра, сохраненного в буфере.|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Задает состояние указанного параметра, сохраненного в буфере.|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Задает строковые данные указанного параметра, сохраненного в буфере.|  
  
## <a name="remarks"></a>Примечания  
 Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.  
  
 Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера можно с помощью методов [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) и [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Пример, демонстрирующий использование этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров, см. в статье базы знаний Q058860, HOWTO: Execute Stored Procedure using CDynamicParameterAccessor (Практическое руководство. Выполнение хранимой процедуры с помощью метода CDynamicParameterAccessor). Статьи базы знаний доступны в документации по Visual Studio библиотеки MSDN или на веб-сайте [http://support.microsoft.com/](http://support.microsoft.com).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:**atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)