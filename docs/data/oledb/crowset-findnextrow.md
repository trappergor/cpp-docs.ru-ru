---
title: CRowset::FindNextRow | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset.FindNextRow
- CRowset<TAccessor>.FindNextRow
- ATL::CRowset::FindNextRow
- CRowset::FindNextRow
- CRowset<TAccessor>::FindNextRow
- CRowset.FindNextRow
- ATL.CRowset<TAccessor>.FindNextRow
- ATL::CRowset<TAccessor>::FindNextRow
- FindNextRow
dev_langs:
- C++
helpviewer_keywords:
- FindNextRow method
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4afc1db20970102ecddb9031f4f1b7a8f6906cf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098229"
---
# <a name="crowsetfindnextrow"></a>CRowset::FindNextRow
Находит сопоставления следующую строку после указанной закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT FindNextRow(DBCOMPAREOP op,   
  BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `op`  
 [in] Операция для использования при сравнении значений строк. Значения см. в разделе [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 [in] Указатель на значение для сравнения.  
  
 `wType`  
 [in] Указывает тип данных значение части буфера. Сведения об индикаторах типа см. в разделе [типы данных](https://msdn.microsoft.com/en-us/library/ms723969.aspx) в *Справочник программиста OLE DB* в Windows SDK.  
  
 `nLength`  
 [in] Длина структуры данных потребителя, выделенное для значения данных в байтах. Дополнительные сведения см. в описании **cbMaxLen** в [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *Справочник программиста OLE DB.*  
  
 `bPrecision`  
 [in] Максимальная точность, при получении данных. Используется, только если `wType` — `DBTYPE_NUMERIC`. Дополнительные сведения см. в разделе [преобразования, включающие DBTYPE_NUMERIC или DBTYPE_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) в *Справочник программиста OLE DB*.  
  
 `bScale`  
 [in] Масштаб, используемый при получении данных. Используется, только если `wType` — `DBTYPE_NUMERIC` или **DBTYPE_DECIMAL**. Дополнительные сведения см. в разделе [преобразования, включающие DBTYPE_NUMERIC или DBTYPE_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) в *Справочник программиста OLE DB*.  
  
 *bSkipCurrent*  
 [in] Количество строк от закладки, с которой начинается поиск.  
  
 `pBookmark`  
 [in] Закладка для позиции, с которой начинается поиск.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод требует дополнительный интерфейс **IRowsetFind**, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetFind** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
 Сведения об использовании закладки в потребителей в разделе [с помощью закладок](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)