---
title: Класс CEnumerator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9f8af45082f8b861b177c4e214a69e9b15799dd7
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233377"
---
# <a name="cenumerator-class"></a>Класс CEnumerator
Использует объект перечисления OLE DB, который предоставляет [ISourcesRowset](https://msdn.microsoft.com/library/ms715969.aspx) интерфейс, чтобы вернуть набор строк, описывающий все источники данных и перечислителей.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[найти](#find)|Перебирает доступных поставщиков (источники данных), поиск с указанным именем.|  
|[GetMoniker](#getmoniker)|Извлекает `IMoniker` интерфейс для текущей записи.|  
|[Открыть](#open)|Открывает перечислитель.|  
  
## <a name="remarks"></a>Примечания  
 Вы можете получить `ISourcesRowset` данных косвенно от этого класса.  

## <a name="find"></a> CEnumerator::Find
Выполняет поиск указанного имени среди доступных поставщиков.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *szSearchName*  
 [in] Имя для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если имя найдено. В противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Это имя сопоставляется `SOURCES_NAME` членом [ISourcesRowset](https://msdn.microsoft.com/library/ms715969.aspx) интерфейс.  
  
## <a name="getmoniker"></a> CEnumerator::GetMoniker
Выполняет синтаксический анализ отображаемое имя извлекаемого компонента строки, который можно преобразовать в моникер.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();  


HRESULT GetMoniker(LPMONIKER* ppMoniker,   
   LPCTSTR lpszDisplayName) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *ppMoniker*  
 [out] Синтаксический анализ моникера из отображаемого имени ([CEnumeratorAccessor::m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) текущей строки.  
  
 *lpszDisplayName*  
 [in] Отображаемое имя для синтаксического анализа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="open"></a> CEnumerator::Open
Привязывает моникера для перечислителя, если один указан, а затем получает набор строк для перечислителя, вызывая [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(LPMONIKER pMoniker) throw();  


HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();  


HRESULT Open(const CEnumerator& enumerator) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pMoniker*  
 [in] Указатель на моникер для перечислителя.  
  
 *pClsid*  
 [in] Указатель на `CLSID` перечислителя.  
  
 *enumerator*  
 [in] Ссылка на перечислитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)