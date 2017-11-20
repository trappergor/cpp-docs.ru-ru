---
title: "Класс IRowsetNotifyImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs: C++
helpviewer_keywords: IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7473e63c7ca67dff200d5cf96f1774ca9a2d6817
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimpl-class"></a>Класс IRowsetNotifyImpl
Реализует и регистрирует [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) на объекте-получателе (также называется «приемник»), чтобы она могла обрабатывать уведомления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|Уведомляет объект-получатель о любом изменении значения столбца.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|Уведомляет объект-получатель о первом изменении строки или обо всех изменениях, которые влияют на всю строку.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|Уведомляет объект-получатель обо всех изменениях, влияющих на весь набор строк.|  
  
## <a name="remarks"></a>Примечания  
 В разделе [получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации точки подключения интерфейса на объекте-получателе.  
  
 `IRowsetNotifyImpl`предоставляет реализацию фиктивный `IRowsetNotify`, с пустым функции для `IRowsetNotify` методы [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), и [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). При наследовании от этого класса, при реализации `IRowsetNotify` интерфейса, можно реализовать только необходимые методы. Необходимо также указать пустые реализации для других методов самостоятельно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [Класс IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)