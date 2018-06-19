---
title: CCommand::SetParameterInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- SetParameterInfo method
ms.assetid: a70e92f4-1e73-41d7-a5b7-c6ebb45a6477
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a1bcbc30564b248991859ca2b1911e7b8a67dbe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094531"
---
# <a name="ccommandsetparameterinfo"></a>CCommand::SetParameterInfo
Задает собственный тип каждого параметра команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,  
   const DBORDINAL* pOrdinals,  
   const DBPARAMBINDINFO* pParamInfo) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommandWithParameters::SetParameterInfo](https://msdn.microsoft.com/en-us/library/ms725393.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)