---
title: Структура CDaoRelationInfo
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: 7d1c86732966d8222582dc6d4527af89963a5cdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152830"
---
# <a name="cdaorelationinfo-structure"></a>Структура CDaoRelationInfo

`CDaoRelationInfo` Структура содержит сведения о связи, определенные между полями двух таблиц [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.

## <a name="syntax"></a>Синтаксис

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет объект отношения. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_strTable*<br/>
Имена главной таблицы в связи.

*m_strForeignTable*<br/>
Имя таблицы внешнего в связи. Внешней таблицы — это таблица, содержащий внешние ключи. Как правило используется внешней таблицы для наложения ссылочной целостности. Внешняя таблица обычно находится на стороне "многие" отношения «один ко многим». Примеры внешних таблиц: таблицы, содержащие коды для American состояний или провинциях Канады или заказов клиентов.

*m_lAttributes*<br/>
Содержит сведения о типе связи. Значение этого элемента может быть любое из следующих:

- `dbRelationUnique` Отношение один к одному.

- `dbRelationDontEnforce` Связь не является включенным (не ограничением ссылочной целостности).

- `dbRelationInherited` Связь существует в базе кадр, который содержит две вложенные таблицы.

- `dbRelationLeft` Связь является левое соединение. Левое внешнее соединение включает в себя все записи из первого (слева) таблицы, даже если они не соответствуют для записей во второй таблице (справа).

- `dbRelationRight` Связь является правильного соединения. Правое внешнее соединение включает в себя все записи из второго (справа) таблицы, даже если они не соответствуют для записей в таблице первого (слева).

- `dbRelationUpdateCascade` Обновления будут нарастать.

- `dbRelationDeleteCascade` Удаление происходит каскадом.

*m_pFieldInfos*<br/>
Указатель на массив [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) структуры. Массив содержит один объект для каждого поля в связи. `m_nFields` Данные-член возвращает количество элементов массива.

*m_nFields*<br/>
Число `CDaoRelationFieldInfo` объекты в `m_pFieldInfos` элемент данных.

## <a name="remarks"></a>Примечания

Ссылки на первичной и вторичной выше указывают, как возвращаются данные по [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена в классе `CDaoDatabase`.

Класс MFC не представлены отношения объектов. Вместо этого, объект DAO, базовый объект MFC `CDaoDatabase` класс содержит коллекцию объектов связи: `CDaoDatabase` предоставляет функции-члены для доступа к некоторых отдельных элементов, сведения о связях, или можно получить доступ к их за один раз с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функция-член края содержащего его объекта базы данных.

Сведений, получаемых методом [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функция-член хранится в `CDaoRelationInfo` структуры. `CDaoRelationInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoRelationInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структура CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)
