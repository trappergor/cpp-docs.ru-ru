---
title: "Обмен полями записей: Работа с кодом мастера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8909a9e933e7b3f1c59fa9ab283706f7a6d1f0c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Обмен данными с полями записей (RFX). Работа с кодом мастера
В этом разделе объясняется, мастер приложений MFC и **добавить класс** (как описано в [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для поддержки RFX и способ изменить этот код.  
  
> [!NOTE]
>  Этот раздел относится к классы, производные от `CRecordset` в какой строке массовая выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. О различиях в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 При создании класса набора записей с помощью мастера приложений MFC или **Добавление класса**, мастер создает следующие элементы RFX для вас, основанный на источнике данных, таблицы и выбора столбцов, отмеченных в мастере:  
  
-   Объявления элементов данных полей набора записей в классе набора записей  
  
-   Переопределение`CRecordset::DoFieldExchange`  
  
-   Инициализация элементов данных полей набора записей в конструкторе класса набора записей  
  
##  <a name="_core_the_field_data_member_declarations"></a>Объявления элементов данных полей  
 Мастер прописывает объявления класса набора записей в h-файле, подобное приведенному ниже, для класса `CSections`:  
  
```  
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
  
 При добавлении элементов данных параметров или нового поля элементов данных, которые вы самостоятельно привязать, их необходимо добавьте после сформированных мастером.  
  
 Кроме того, обратите внимание, что мастер переопределяет `DoFieldExchange` функции-члена класса `CRecordset`.  
  
##  <a name="_core_the_dofieldexchange_override"></a>DoFieldExchange переопределения  

 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) является сердцем RFX. Платформа вызывает `DoFieldExchange` любое время, необходимое для перемещения данных из источника данных в набор записей, либо из набора записей в источник данных. `DoFieldExchange`также поддерживает получение сведений о поле членов данных с помощью [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) и [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) функции-члены.  
  
 Следующие `DoFieldExchange` — переопределение для `CSections` класса. Мастер записывает функцию в CPP-файл для класса набора записей.  
  
```  
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
  
 Обратите внимание, следующие основные возможности функции:  
  
-   В этом разделе функция вызывается сопоставления полей.  
  
-   Вызов `CFieldExchange::SetFieldType`, с помощью `pFX` указателя. Этот вызов указывает, что все вызовы функций RFX до конца `DoFieldExchange` или при следующем вызове `SetFieldType` выходных столбцов. Дополнительные сведения см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
-   Несколько вызовов `RFX_Text` глобальной функции — по одной на каждый элемент поля данных (все они являются `CString` перемен в примере). Эти вызовы определяют связь между именем столбца в источнике данных и элементом поля данных. Функции RFX выполняют реальное перемещение данных. Библиотека классов предоставляет функции RFX для основных типов данных. Дополнительные сведения о функциях RFX см. в разделе [обмен полями записей: использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  Порядок столбцов в результирующий набор должен соответствовать порядку вызовов функции RFX в `DoFieldExchange`.  
  
-   `pFX` Указатель [разделе](../../mfc/reference/cfieldexchange-class.md) объект, который передается платформой, когда она вызывает `DoFieldExchange`. `CFieldExchange` Объекта указывает операцию, `DoFieldExchange` выполнить, направление передачи и другой контекстной информации.  
  
##  <a name="_core_the_recordset_constructor"></a>Конструктор набора записей  
 Написанный мастером конструктор набора записей содержит две вещи, относящиеся к RFX:  
  
-   Инициализацию для каждого элемента данных поля  
  
-   Инициализацию для [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) элемента данных, которое содержит количество элементов данных полей  
  
 Конструктор `CSections` примера набора записей выглядит следующим образом:  
  
```  
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
>  Если элементы поля данных добавляются вручную, например, чтобы выполнить динамическую привязку новых столбцов, необходимо увеличить `m_nFields`. Для этого добавлением строки кода, такие как:  
  
```  
m_nFields += 3;  
```  

 Это код для добавления трех новых полей. При добавлении элементов данных параметров, следует инициализировать [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) элемента данных, которое содержит количество элементов данных параметров. Поместите `m_nParams` за скобки.  

  
## <a name="see-also"></a>См. также  
 [Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)