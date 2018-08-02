---
title: Класс CRestrictions | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4d93d1042f48ae877e61692b095be9442f9a7917
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337181"
---
# <a name="crestrictions-class"></a>Класс CRestrictions
Универсальный класс, который позволяет указать ограничения для наборов строк схемы.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
   public CSchemaRowset <T, nRestrictions>  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, используемый для метода доступа.  
  
 *nRestrictions*  
 Число столбцов ограничений для набора строк схемы.  
  
 *pguid*  
 Указатель на идентификатор GUID для схемы.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h 
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Открыть](#open)|Возвращает результирующий набор в соответствии с ограничения, предоставленное пользователем.|   

## <a name="open"></a> CRestrictions::Open
Возвращает результирующий набор в соответствии с ограничения, предоставленное пользователем.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Сеанс*  
 [in] Указывает существующий объект сеанса, используемый для подключения к источнику данных.  
  
 *lpszParam*  
 [in] Задает ограничения в наборе строк схемы.  
  
 *bBind*  
 [in] Указывает, нужно ли автоматически привязывать сопоставление столбцов. По умолчанию используется **true**, что приводит в сопоставление столбцов, автоматически привязываться. Установка *bBind* для **false** предотвращает автоматическое связывание сопоставление столбцов, можно привязать вручную. (Привязке вручную является особый интерес для пользователей OLAP).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Можно указать максимум семь ограничений в наборе строк схемы.  
  
 См. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) сведения об определенных ограничениях на все наборы строк схемы.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны OLE DB потребителя](../../data/oledb/ole-db-consumer-templates-reference.md)    
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)