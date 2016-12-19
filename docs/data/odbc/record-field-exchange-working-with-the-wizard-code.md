---
title: "Обмен данными с полями записей (RFX). Работа с кодом мастера | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoFieldExchange - метод, переопределение"
  - "члены данных полей"
  - "члены данных полей, объявление"
  - "m_nFields - элемент данных"
  - "m_nFields - элемент данных, инициализация"
  - "m_nParams - элемент данных"
  - "m_nParams - элемент данных, инициализация"
  - "ODBC, RFX"
  - "переопределение, DoFieldExchange"
  - "RFX (ODBC), реализация"
  - "RFX (ODBC), код мастера"
  - "Юникод, с помощью классов баз данных"
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обмен данными с полями записей (RFX). Работа с кодом мастера
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе объясняется написание кода для RFX с помощью мастера приложения MFC и **Добавление класса** \(как описано в разделе [Добавление объекта\-получателя MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\), а также его изменение.  
  
> [!NOTE]
>  В этом разделе описываются классы, производные от `CRecordset`, в которых не была реализована групповая выборка строк.  При использовании групповой выборки строк реализуется групповой обмен данными с полями записей \(групповой RFX\).  Групповой RFX и обычный RFX похожи.  Описание различий см. в разделе [Набор записей: групповая выборка записей ODBC](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md).  
  
 При создании класса набора записей с помощью мастера приложений MFC или возможности **Добавление класса**, мастер создает следующие элементы RFX на основе источника данных, таблицы и выбора столбцов, отмеченных в мастере:  
  
-   Объявления элементов полей с данными набора записей в классе набора записей  
  
-   Переопределение `CRecordset::DoFieldExchange`  
  
-   Инициализация элементов полей с данными набора записей в конструкторе класса набора записей  
  
##  <a name="_core_the_field_data_member_declarations"></a> Объявления элементов полей с данными  
 Мастер прописывает объявления класса набора записей в H\-файле, который похож на класс `CSections`, следующим образом:  
  
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
  
 При добавлении элементов данных параметров или создании элементов полей с данными их следует добавить после сформированных мастером.  
  
 Также следует обратить внимание на то, что мастер переопределяет функцию\-член `DoFieldExchange` класса `CRecordset`.  
  
##  <a name="_core_the_dofieldexchange_override"></a> Переопределение DoFieldExchange  
 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) является основой RFX.  Платформа вызывает `DoFieldExchange` каждый раз, когда требуется переместить данные либо из источника данных в набор записей, либо из набора записей в источник данных.  `DoFieldExchange` также поддерживает получение информации об элементах данных полей с помощью функций\-членов [IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md) и [IsFieldNull](../Topic/CRecordset::IsFieldNull.md).  
  
 Ниже приводится переопределение `DoFieldExchange` для класса `CSections`.  Мастер записывает функцию в .СРР\-файл для класса набора записей.  
  
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
  
 Обратите внимание на следующие ключевые возможности функции:  
  
-   Эта секция функции называется сопоставлением поля.  
  
-   Вызов `CFieldExchange::SetFieldType` с помощью указателя `pFX`.  Этот вызов указывает, что все вызовы функций RFX до конца `DoFieldExchange` либо следующий вызов `SetFieldType` являются столбцами вывода.  Дополнительные сведения см. в описании [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md).  
  
-   Несколько вызовов глобальной функции `RFX_Text` — по одному на каждый элемент поля данных \(все они являются переменными типа `CString` в данном примере\).  Эти вызовы определяют связь между именем столбца в источнике данных и элементом поля данных.  Функции RFX выполняют реальное перемещение данных.  Библиотека классов предоставляет функции RFX для всех распространенных типов данных.  Дополнительные сведения о функциях RFX см. в разделе [Обмен данными с полями записей. Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  Порядок столбцов полученного результата должен соответствовать порядку вызовов функции RFX в `DoFieldExchange`.  
  
-   Указатель `pFX` на объект [CFieldExchange](../../mfc/reference/cfieldexchange-class.md), который передается платформой, когда она вызывает `DoFieldExchange`.  Объект `CFieldExchange` указывает операцию, которую необходимо `DoFieldExchange` выполнить, направление перемещения и другую контекстную информацию.  
  
##  <a name="_core_the_recordset_constructor"></a> Конструктор набора записей  
 Написанный мастером конструктор набора записей содержит две вещи, относящиеся к RFX:  
  
-   Инициализацию для каждого элемента поля данных  
  
-   Инициализацию для элемента данных [m\_nFields](../Topic/CRecordset::m_nFields.md), который содержит число элементов поля данных  
  
 Конструктор для примера набора записей `CSections` представлен таким образом:  
  
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
>  Если элементы поля данных добавляются вручную, например, чтобы выполнить динамическую привязку столбца, необходимо увеличить `m_nFields`.  Это можно сделать добавлением строки кода, такого как:  
  
```  
m_nFields += 3;  
```  
  
 Этот код добавляет три новых поля.  При добавлении элементов данных параметров, следует инициализировать элемент данных [m\_nParams](../Topic/CRecordset::m_nParams.md), который содержит количество элементов данных параметров.  Вынесите настройку `m_nParams` за скобки.  
  
## См. также  
 [Обмен данными полями записей \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)