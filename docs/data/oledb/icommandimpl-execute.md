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
ms.openlocfilehash: 84ff5892573f2bb1fc80f7eb88e21948df561fc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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