---
title: "ICommandImpl::CreateRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 45fcb53c6412f91c35ea26a5e7a732f5de2d3fcc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
Вызывается методом [Execute](../../data/oledb/icommandimpl-execute.md) для создания одного набора строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Параметры  
 `RowsetClass`  
 Член класса шаблона, представляющий пользователя класса набора строк. Как правило, создаются с помощью мастера.  
  
 `pUnkOuter`  
 [in] Указатель на управление **IUnknown** интерфейс, если в ходе статистической обработки, создается набор строк; в противном случае имеет значение null.  
  
 `riid`  
 [in] Соответствует `riid` в `ICommand::Execute`.  
  
 `pParams`  
 [входные/выходные] Соответствует `pParams` в `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Соответствует `pcRowsAffected` в `ICommand::Execute`.  
  
 `ppRowset`  
 [входные/выходные] Соответствует `ppRowset` в `ICommand::Execute`.  
  
 `pRowsetObj`  
 [out] Указатель на объект набора строк. Обычно этот параметр не используется, но он может использоваться, если в наборе строк, необходимо выполнить дополнительные действия до его передачи в COM-объект. Время существования `pRowsetObj` , ограничивается `ppRowset`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . В разделе `ICommand::Execute` список типичных значений.  
  
## <a name="remarks"></a>Примечания  
 Для создания нескольких строк или имеют собственные условия для создания различных наборов строк, поместите различные вызовы `CreateRowset` изнутри **Execute**.  
  
 В разделе [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) в *справочника программиста OLE DB.*  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandImpl](../../data/oledb/icommandimpl-class.md)