---
title: Класс CRestrictions
ms.date: 11/04/2016
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
ms.openlocfilehash: 95517931f3156c4850e07c78910ccbffff424faa
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556521"
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

*T*<br/>
Класс, используемый для метода доступа.

*nRestrictions*<br/>
Число столбцов ограничений для набора строк схемы.

*pguid*<br/>
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

*Сеанс*<br/>
[in] Указывает существующий объект сеанса, используемый для подключения к источнику данных.

*lpszParam*<br/>
[in] Задает ограничения в наборе строк схемы.

*bBind*<br/>
[in] Указывает, нужно ли автоматически привязывать сопоставление столбцов. По умолчанию используется **true**, что приводит в сопоставление столбцов, автоматически привязываться. Установка *bBind* для **false** предотвращает автоматическое связывание сопоставление столбцов, можно привязать вручную. (Привязке вручную является особый интерес для пользователей OLAP).

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Можно указать максимум семь ограничений в наборе строк схемы.

См. в разделе [IDBSchemaRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms713686(v=vs.85)) сведения об определенных ограничениях на все наборы строк схемы.

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)