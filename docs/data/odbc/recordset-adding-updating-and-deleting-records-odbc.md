---
title: Набор записей. Добавление, обновление и удаление записей (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
ms.openlocfilehash: 628ffb2feee385a4114b0dbea074f81678c529d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367107"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Набор записей. Добавление, обновление и удаление записей (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

> [!NOTE]
> Теперь вы можете добавлять записи навалом более эффективно. Для получения дополнительной информации [см. Recordset: Добавление записей в массовых (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).

> [!NOTE]
> Этот раздел относится к объектам, производным от `CRecordset`, в которых пакетное получение строк не реализовано. Если вы используете объем строки извлечения, см [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Обновляемые снимки и динасеты позволяют добавлять, отсеивать (обновлять) и удалять записи. В этом разделе рассматриваются следующие вопросы.

- [Как определить, является ли ваш рекорд.](#_core_determining_whether_your_recordset_is_updatable)

- [Как добавить новую запись](#_core_adding_a_record_to_a_recordset).

- [Как отсеять существующую запись](#_core_editing_a_record_in_a_recordset).

- [Как удалить запись](#_core_deleting_a_record_from_a_recordset).

Для получения дополнительной информации о том, как обновления выполняются и как ваши обновления появляются для других пользователей, [см.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) Обычно при добавлении, изменении или удалении записи запись немедленно изменяет источник данных. Вместо этого можно вложить группы связанных обновлений в транзакции. Если транзакция выполняется, обновление не становится окончательным до тех пор, пока вы не совершите транзакцию. Это позволяет отбросить или откатить изменения. Для получения информации [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)о транзакциях см.

В следующей таблице кратко излагаются параметры, доступные для записей с различными характеристиками обновления.

### <a name="recordset-readupdate-options"></a>Параметры чтения/обновления

|Тип|Чтение|Изменение записи|Удаление записи|Добавление нового (приложения)|
|----------|----------|-----------------|-------------------|------------------------|
|Только для чтения|Да|Нет|Нет|Нет|
|Только приприбор|Да|Нет|Нет|Да|
|Полностью updatable|Да|Да|Да|Да|

## <a name="determining-whether-your-recordset-is-updateable"></a><a name="_core_determining_whether_your_recordset_is_updatable"></a>Определение того, является ли ваш набор записей обновляемым

Объект записи обновляется, если источник данных обновляется, и вы открыли запись как обновляемый. Его обновление также зависит от оператора S'L, который вы используете, возможностей драйвера ODBC и того, является ли библиотека ODBC Cursor в памяти. Нельзя обновлять набор записей только для чтения или источник данных.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>Определить, является ли ваш рекорд

1. Вызовите функцию члена [canUpdate](../../mfc/reference/crecordset-class.md#canupdate) объекта записи.

   `CanUpdate`возвращает ненулевое значение, если набор записей обновляется.

По умолчанию записи полностью обновляются `AddNew` `Edit`(можно `Delete` выполнять и выполнять операции). Но вы также можете использовать [опцию appendOnly](../../mfc/reference/crecordset-class.md#open) для открытия обновляемых записей. Рекордсет открыл таким образом позволяет только добавление `AddNew`новых записей с . Вы не можете отсеивать или удалять существующие записи. Вы можете проверить, открыт ли набор записей только для приложения, позвонив в функцию участника [CanAppend.](../../mfc/reference/crecordset-class.md#canappend) `CanAppend`возвращает ненулевое значение, если запись либо полностью обновляется, либо открыта только для добавления.

Следующий код показывает, `CanUpdate` как можно использовать `rsStudentSet`для объекта, называемого рекордным:

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
> Когда вы готовитесь обновить `Update`набор записей, позвонив, позаботьтесь о том, чтобы ваш набор включает в себя все столбцы, составляющие основной ключ таблицы (или все столбцы любого уникального индекса на столе). В некоторых случаях фреймворк может использовать только выбранные в записи столбцы, чтобы определить, какую запись в таблице обновлять. Без всех необходимых столбцов несколько записей могут быть обновлены в таблице, что, возможно, нанесет ущерб референциальной целостности таблицы. В этом случае фреймворк выбрасывает исключения при вызове. `Update`

## <a name="adding-a-record-to-a-recordset"></a><a name="_core_adding_a_record_to_a_recordset"></a>Добавление записи в набор записей

Вы можете добавить новые записи в рекордный набор, если его функция члена [CanAppend](../../mfc/reference/crecordset-class.md#canappend) возвращает ненулевое значение.

#### <a name="to-add-a-new-record-to-a-recordset"></a>Добавление новой записи к рекорду

1. Убедитесь, что набор записей придатим.

1. Вызовите функцию [addNew-участника](../../mfc/reference/crecordset-class.md#addnew) объекта записи.

   `AddNew`готовит рекорддля, чтобы выступать в качестве буфера для отодействия. Все участники полевых данных настроены на специальное значение Null и помечены как неизмененные, поэтому измененные (грязные) значения записываются в источник данных при вызове [Update.](../../mfc/reference/crecordset-class.md#update)

1. Установите значения полевых данных новых членов записи.

   Присваивай значения членам данных на местах. Те, кого вы не назначаете, не записаны в источник данных.

1. Вызовите функцию `Update` члена объекта записи.

   `Update`завершает добавление, написав новую запись в источник данных. Для получения информации о `Update`случае происходит, если вы не звоните, см [Recordset: Как записи обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Для получения информации о [том,](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)как работают добавления записей и о том, когда добавленные записи видны в вашем наборе рекордов, см.

В следующем примере показано, как добавить новую запись:

```cpp
if( !rsStudent.Open( ) )
    return FALSE;
if( !rsStudent.CanAppend( ) )
    return FALSE;                      // no field values were set
rsStudent.AddNew( );
rsStudent.m_strName = strName;
rsStudent.m_strCity = strCity;
rsStudent.m_strStreet = strStreet;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not added; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> Чтобы `AddNew` отменить `Edit` вызов или звонок, `AddNew` `Edit` просто `Move` сделайте еще один звонок или позвоните по *AFX_MOVE_REFRESH* параметру. Участники данных сбросить их предыдущие значения, `Edit` `Add` и вы все еще в режиме или режиме.

## <a name="editing-a-record-in-a-recordset"></a><a name="_core_editing_a_record_in_a_recordset"></a>Редактирование записи в наборе рекордов

Вы можете отсеивать существующие записи, если функция участника [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) вашего записи возвращает ненулевое значение.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>Для отсечения существующей записи в рекордном наборе

1. Убедитесь, что рекорд может быть обновлен.

1. Прокрутите запись, которая требуется обновить.

1. Вызовите функцию [редактирует](../../mfc/reference/crecordset-class.md#edit) объект записи.

   `Edit`готовит рекорддля, чтобы выступать в качестве буфера для отодействия. Все полевых данных помечены таким образом, чтобы рекордсет мог позже сказать, были ли они изменены. Новые значения для измененных членов полевых данных записываются в источник данных при вызове [Update.](../../mfc/reference/crecordset-class.md#update)

1. Установите значения полевых данных новых членов записи.

   Присваивай значения членам данных на местах. Те, которые вы не присваиваете значения, остаются неизменными.

1. Вызовите функцию `Update` члена объекта записи.

   `Update`завершает изменение, написав измененную запись в источник данных. Для получения информации о `Update`случае происходит, если вы не звоните, см [Recordset: Как записи обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

После редактирования записи отредактированная запись остается текущей записью.

В следующем примере показана `Edit` операция. Предполагается, что пользователь перешел на запись, которая он или она хочет отсеить.

```cpp
rsStudent.Edit( );
rsStudent.m_strStreet = strNewStreet;
rsStudent.m_strCity = strNewCity;
rsStudent.m_strState = strNewState;
rsStudent.m_strPostalCode = strNewPostalCode;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not updated; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> Чтобы `AddNew` отменить `Edit` вызов или звонок, `AddNew` `Edit` просто `Move` сделайте еще один звонок или позвоните по *AFX_MOVE_REFRESH* параметру. Участники данных сбросить их предыдущие значения, `Edit` `Add` и вы все еще в режиме или режиме.

## <a name="deleting-a-record-from-a-recordset"></a><a name="_core_deleting_a_record_from_a_recordset"></a>Удаляние записи из рекордного набора

Вы можете удалить записи, если функция участника [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) вашего записного набора возвращает ненулевое значение.

#### <a name="to-delete-a-record"></a>Удаление записи

1. Убедитесь, что рекорд может быть обновлен.

1. Прокрутите запись, которая требуется обновить.

1. Вызовите функцию [участника удаления](../../mfc/reference/crecordset-class.md#delete) объекта записи.

   `Delete`сразу же отмечает запись как удаленную, как в наборе записей, так и в источнике данных.

   В `AddNew` `Edit`отличие `Delete` от `Update` и, не имеет соответствующего вызова.

1. Прокрутите другую запись.

   > [!NOTE]
   >  При перемещении по набору записей удаленные записи могут не быть пропущены. Для получения дополнительной [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) информации см.

В следующем примере показана `Delete` операция. Предполагается, что пользователь перешел на запись, которую пользователь хочет удалить. После `Delete` вызова важно перейти к новой записи.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

Для получения дополнительной информации `AddNew` `Edit`о `Delete` последствиях , и функции членов, см. [Recordset: Как записи обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей: блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
