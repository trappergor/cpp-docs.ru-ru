---
title: "CUtlProps::OnInterfaceRequested | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CUtlProps
dev_langs: C++
helpviewer_keywords: OnInterfaceRequested method
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c458eaf7c1e41ade5d29fa020bacfebb2b278e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsoninterfacerequested"></a>CUtlProps::OnInterfaceRequested
Обрабатывает запросы к дополнительный интерфейс, когда потребитель вызывает метод для одного объекта создания интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(  
   REFIID riid  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Дополнительные сведения см. в описании `riid` параметр `ICommand::Execute` в *Справочник программиста OLE DB* (в *MDAC SDK*).  
  
## <a name="remarks"></a>Примечания  
 **OnInterfaceRequested** обрабатывает запросы потребителя дополнительный интерфейс, когда потребитель вызывает метод для одного объекта создания интерфейсов (такие как **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset`, или `ICommand`). Он задает соответствующее свойство OLE DB для запрошенного интерфейса. Например, если потребитель запрашивает **IID_IRowsetLocate**, **OnInterfaceRequested** задает **DBPROP_IRowsetLocate** интерфейса. Это обеспечивает правильное состояние во время создания набора строк.  
  
 Этот метод вызывается, когда пользователь вызывает **IOpenRowset::OpenRowset** или `ICommand::Execute`.  
  
 Если потребитель открывает объект и запрашивает дополнительный интерфейс, поставщик следует установить свойство, связанное с этот интерфейс для `VARIANT_TRUE`. Разрешить обработку свойств **OnInterfaceRequested** вызывается перед поставщика **Execute** вызывается метод. По умолчанию **OnInterfaceRequested** обрабатывает следующие интерфейсы:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 При необходимости обработки других интерфейсов, переопределите эту функцию в классе источника, сеанса, команды или набора строк данных позволяет функции процесса. Переопределения должны проходить через интерфейсы свойства обычного set или get для убедитесь, что задание свойств устанавливает какие-либо связанные свойства (в разделе [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)