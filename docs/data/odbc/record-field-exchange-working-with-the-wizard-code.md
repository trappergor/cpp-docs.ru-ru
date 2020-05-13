---
title: Обмен данными с полями записей (RFX). Работа с кодом мастера
ms.date: 05/09/2019
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
ms.openlocfilehash: 8e42fc9da672ca4ef97e775776935650ab7f545a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367119"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Обмен данными с полями записей (RFX). Работа с кодом мастера

> [!NOTE]
> Мастер потребителя MFC ODBC недоступен в Visual Studio 2019 и более поздних версиях. При этом вы по-прежнему можете создать потребитель вручную.

В этом разделе объясняется код, который мастер приложений MFC и мастер **Добавления класса** (как описано в разделе [Добавление объекта-получателя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) пишет для поддержки RFX, и то, как можно изменить этот код.

> [!NOTE]
> Этот раздел относится к классам, производным от `CRecordset`, в которых пакетное получение строк не реализовано. Если вы используете пакетное получение строк, реализуется пакетный обмен полями записей (Bulk RFX). Bulk RFX аналогичен RFX. Чтобы понять различия, [см.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

При создании класса набора записей с помощью мастера приложений MFC или мастера **Добавления класса** мастер создает следующие элементы, связанные с RFX, на основе параметров источника данных, таблицы и столбцов, выбранных вами в мастере:

- Объявления элементов данных полей набора записей в классе наборов записей

- Переопределение `CRecordset::DoFieldExchange`

- Инициализация элементов данных полей набора записей в конструкторе класса набора записей

## <a name="field-data-member-declarations"></a><a name="_core_the_field_data_member_declarations"></a> Объявления элементов данных полей

Мастера прописывают объявления класса набора записей в H-файле, подобном приведенному ниже, для класса `CSections`:

```cpp
class CSections : public CRecordset
{
public:
   CSections(CDatabase* pDatabase = NULL);
   DECLARE_DYNAMIC(CSections)

// Field/Param Data
   CString   m_strCourseID;
   CString   m_strInstructorID;
   CString   m_strRoomNo;
   CString   m_strSchedule;
   CString   m_strSectionNo;

// Overrides
   // Wizard generated virtual function overrides
   protected:
   virtual CString GetDefaultConnect();  // Default connection string
   virtual CString GetDefaultSQL();      // Default SQL for Recordset
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support

// Implementation
#ifdef _DEBUG
   virtual void AssertValid() const;
   virtual void Dump(CDumpContext& dc) const;
#endif

};
```

Если вы добавляете элементы данных параметров или новые элементы данных полей, которые вы привязываете самостоятельно, их необходимо добавить после созданных мастером.

Кроме того, обратите внимание, что мастер переопределяет функцию элемента `DoFieldExchange` класса `CRecordset`.

## <a name="dofieldexchange-override"></a><a name="_core_the_dofieldexchange_override"></a> Переопределение DoFieldExchange

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) является сердцем RFX. Платформа вызывает `DoFieldExchange` в любое время, когда нужно переместить данные из источника данных в набор записей или из набора записей в источник данных. `DoFieldExchange` также поддерживает получение сведений об элементах данных полей через функции элементов [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) и [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).

Следующее переопределение `DoFieldExchange` предназначено для класса `CSections`. Мастер создает функцию в CPP-файле для класса набора записей.

```cpp
void CSections::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Text(pFX, "CourseID", m_strCourseID);
   RFX_Text(pFX, "InstructorID", m_strInstructorID);
   RFX_Text(pFX, "RoomNo", m_strRoomNo);
   RFX_Text(pFX, "Schedule", m_strSchedule);
   RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Обратите внимание на следующие ключевые особенности функции.

- Этот раздел функции называется сопоставлением полей.

- Вызов к `CFieldExchange::SetFieldType` через указатель `pFX`. Этот вызов указывает, что все вызовы функций RFX до конца `DoFieldExchange` или следующего вызова `SetFieldType` являются выходными столбцами. Дополнительные сведения см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Несколько вызовов к глобальной функции `RFX_Text` — один на каждый элемент данных полей (все из которых являются переменными `CString` в примере). Эти вызовы определяют связь между именем столбца в источнике данных и элементом данных поля. Функции RFX выполняют фактическую передачу данных. Библиотека классов предоставляет функции RFX для всех распространенных типов данных. Для получения дополнительной информации [Record Field Exchange: Using the RFX Functions](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)о функциях RFX см.

    > [!NOTE]
    >  Порядок столбцов результирующего набора должен соответствовать порядку вызовов функций RFX в `DoFieldExchange`.

- Указатель `pFX` на объект [CFieldExchange](../../mfc/reference/cfieldexchange-class.md), который передается платформой при вызове `DoFieldExchange`. Объект `CFieldExchange` указывает операцию, которую `DoFieldExchange` собирается выполнить, направление передачи и другие сведения о контексте.

## <a name="recordset-constructor"></a><a name="_core_the_recordset_constructor"></a> Конструктор набора записей

Конструктор набора записей, который записывает мастер, содержит два элемента, связанных с RFX:

- Инициализация для каждого элемента данных поля

- Инициализация для элемента данных [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields), который содержит количество элементов данных полей

Конструктор для примера набора записей `CSections` выглядит следующим образом:

```cpp
CSections::CSections(CDatabase* pdb)
   : CRecordset(pdb)
{
   m_strCourseID = "";
   m_strInstructorID = "";
   m_strRoomNo = "";
   m_strSchedule = "";
   m_strSectionNo = "";
   m_nFields = 5;
}
```

> [!NOTE]
> Если вы добавляете элементы данных полей вручную, как это делается, например, при динамической привязке новых столбцов, необходимо увеличить `m_nFields`. Для этого добавьте другую строку кода, например:

```cpp
m_nFields += 3;
```

Это код для добавления трех новых полей. При добавлении элементов данных параметров необходимо инициализировать элемент данных [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams), который содержит количество элементов данных параметров. Поместите инициализацию `m_nParams` за скобки.

## <a name="see-also"></a>См. также раздел

[Рекордная полевая биржа (RFX)](../../data/odbc/record-field-exchange-rfx.md)
