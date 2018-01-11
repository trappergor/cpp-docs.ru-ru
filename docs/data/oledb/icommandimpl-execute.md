---
title: "ICommandImpl::Execute | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs: C++
helpviewer_keywords: Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 965a344b55b6d290f112970ff357f383fefcd630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Выполняет команду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Исходящий интерфейс, запрошенный будет получен из объекта набора строк, эта функция создает интерфейс.  
  
 **Выполнение** вызовы [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Переопределите реализацию по умолчанию для создания нескольких строк или имеют собственные условия для создания различных наборов строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Icommandimpl-класс](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)