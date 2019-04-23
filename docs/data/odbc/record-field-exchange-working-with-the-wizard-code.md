---
title: 'Обмен полями записей: Работа с кодом мастера'
ms.date: 11/04/2016
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
ms.openlocfilehash: 82f0d946cac3429150250e2df5d1bfd674ec30ee
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041297"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Обмен полями записей: Работа с кодом мастера

В этом разделе объясняется, мастер приложений MFC и **Добавление класса** (как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для поддержки RFX и как может потребоваться изменить этот код.

> [!NOTE]
>  Этот раздел относится к классам, производным от `CRecordset` в какой строке массовой выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. Сведения о различиях, см. в разделе [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

При создании класса набора записей с помощью мастера приложений MFC или **Добавление класса**, мастер создает следующие элементы RFX, вы, основанный на источнике данных, таблицы и выбора столбцов, вносимые в мастере:

- Объявления поля элементов данных набора записей в классе наборов записей

- Переопределение `CRecordset::DoFieldExchange`

- Инициализация элементов данных полей набора записей в конструкторе класса набора записей

##  <a name="_core_the_field_data_member_declarations"></a> Объявления членов данных поля

Мастер прописывает объявления класса набора записей в h-файле, подобное приведенному ниже, для класса `CSections`:

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

При добавлении элементов данных параметров или нового поля элементов данных, которые можно выполнить привязку самостоятельно, их необходимо добавьте после указанных созданный мастером.

Кроме того, обратите внимание, что мастер переопределяет `DoFieldExchange` функция-член класса `CRecordset`.

##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange переопределения

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) является сердцем RFX. Платформа вызывает `DoFieldExchange` любое время, необходимое для перемещения данных из источника данных в набор записей или из набора записей в источнике данных. `DoFieldExchange` также поддерживает получение сведений о поле членов данных посредством [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) и [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) функций-членов.

Следующие `DoFieldExchange` является переопределение для `CSections` класса. Мастер создает функцию в CPP-файл для класса набора записей.

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

Обратите внимание, что следующие ключевые функции:

- В этом разделе она называется сопоставление полей.

- Вызов `CFieldExchange::SetFieldType`помощи `pFX` указатель. Этот вызов указывает, что все вызовы функций RFX до конца массива `DoFieldExchange` или следующего вызова `SetFieldType` выходных столбцов. Дополнительные сведения см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Несколько вызовов `RFX_Text` глобальной функции — один на каждый элемент поля данных (все из которых `CString` переменных в примере). Эти вызовы определяют связь между именем столбца в источнике данных и элементом поля данных. Функции RFX выполняют передачи фактических данных. Библиотека классов предоставляет функции RFX для всех распространенных типов данных. Дополнительные сведения о функции RFX см. в разделе [обмен полями записей: Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  Порядок столбцов результирующего набора должен соответствовать порядку вызовов функции RFX в `DoFieldExchange`.

- `pFX` Указатель на [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) объект, который передается платформой, когда он вызывает `DoFieldExchange`. `CFieldExchange` Объекта указывает операцию, `DoFieldExchange` выполнить, направление передачи и другие сведения о контексте.

##  <a name="_core_the_recordset_constructor"></a> Конструктор набора записей

Конструктор набора записей, написанный мастером содержит две вещи, связанные с RFX:

- Инициализацию для каждого элемента данных поля

- Инициализацию для [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) данными-членом, состоящем из поля элементов данных

Конструктор `CSections` пример набора записей выглядит следующим образом:

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
>  Если элементы поля данных добавляются вручную, как это делается, чтобы выполнить динамическую привязку новые столбцы, необходимо увеличить `m_nFields`. Сделать это с добавлением строки кода, таких как:

```cpp
m_nFields += 3;
```

Это код для добавления трех новых полей. При добавлении элементов данных параметров, необходимо инициализировать [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) элемент данных, который содержит количество элементов данных параметров. Поместите `m_nParams` за скобки.

## <a name="see-also"></a>См. также

[Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)