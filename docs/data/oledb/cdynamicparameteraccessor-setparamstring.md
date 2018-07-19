---
title: CDynamicParameterAccessor::SetParamString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs:
- C++
helpviewer_keywords:
- SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0b8c435fea707317c1f8de798796f49cb8b048ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095733"
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
Задает строковые данные указанного параметра, сохраненного в буфере.  
  
## <a name="syntax"></a>Синтаксис  
  
```
bool SetParamString(DBORDINAL nParam,   
   constCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,   
   constWCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nParam`  
 [in] Номер параметра (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером — это индекс параметра, в зависимости от порядка в SQL или хранимой процедуры. В разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) в качестве примера.  
  
 `pString`  
 [in] Указатель на ANSI (**CHAR**) или Юникод (**WCHAR**) строковые данные указанного параметра. В разделе `DBSTATUS` в oledb.h.  
  
 *status*  
 [in] `DBSTATUS` Состояние указанного параметра. Сведения о `DBSTATUS` значения, в разделе [состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB*, или выполните поиск `DBSTATUS` в oledb.h.  
  
## <a name="remarks"></a>Примечания  
 Возвращает **true** в случае успешного выполнения или **false** при сбое.  
  
 `SetParamString` завершится ошибкой при попытке задать строку, размер которого превышает максимальный размер, указанный для `pString`.  
  
 Используйте `SetParamString` для задания параметров строковые данные в буфере. Используйте [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) Установка нестроковые данные параметров в буфере.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)