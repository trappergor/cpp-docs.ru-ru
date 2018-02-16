---
title: "CDynamicParameterAccessor::SetParam | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
dev_langs:
- C++
helpviewer_keywords:
- SetParam method
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c6868c9ced5524dcd218d61206c3993ccadd7f8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessorsetparam"></a>CDynamicParameterAccessor::SetParam
Задает параметр буфера, используя указанные данные (без строк).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
               constctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
               const ctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `ctype`  
 Параметр шаблона, тип данных.  
  
 `nParam`  
 [in] Номер параметра (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером — это индекс параметра, в зависимости от порядка в SQL или хранимой процедуры. Пример:  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 [in] Имя параметра.  
  
 `pData`  
 [in] Указатель памяти, содержащий данные для записи в буфер.  
  
 *status*  
 [in] `DBSTATUS` Состояние столбца. Сведения о `DBSTATUS` значения, в разделе [состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB*, или выполните поиск `DBSTATUS` в oledb.h.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения или **false** при сбое.  
  
 Используйте `SetParam` Установка нестроковые данные параметров в буфере. Используйте [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) для задания параметров строковые данные в буфере.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)