---
title: "Обмен полями записей: Использование функций RFX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a270b26fc0fd9be721ee0656f9f0d14ab579b477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Обмен полями записей. Использование функций RFX
В этом разделе описывается использование функции RFX, составляющих тело вашей `DoFieldExchange` переопределения.  
  
> [!NOTE]
>  Этот раздел относится к классы, производные от [CRecordset](../../mfc/reference/crecordset-class.md) в какой строке массовая выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. О различиях в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Глобальные функции RFX обмен данными между столбцами, элементам данных источника и полей данных в наборе записей. Записывать вызовы функций RFX в наборе записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) функции-члена. В этом разделе кратко описаны функции и показаны типы данных, для RFX доступных функций. [Технические примечания 43](../../mfc/tn043-rfx-routines.md) рассматривается написание функций RFX для дополнительных типов данных.  
  
##  <a name="_core_rfx_function_syntax"></a>Синтаксис функции RFX  
 Каждая функция RFX принимает три параметра (и некоторые имеют дополнительный четвертый и пятый параметр):  
  
-   Указатель на [разделе](../../mfc/reference/cfieldexchange-class.md) объекта. Следует просто передать `pFX` указатель передан в `DoFieldExchange`.  
  
-   Имя столбца, как он отображается в источнике данных.  
  
-   Имя соответствующего элемента данных поля или элемента данных параметра в классе набора записей.  
  
-   (Необязательно) В некоторых функций, максимальная длина строки или массива, передаваемый. По умолчанию используется 255 байт, но может потребоваться изменить его. Максимальный размер зависит от максимального размера `CString` объекта — **INT_MAX** (2 147 483 647) байт — но, вероятно, приведет к ограничивается драйвера.  
  
-   (Необязательно) В `RFX_Text` функции, иногда пятый параметр используется для указания типа данных столбца.  
  
 Дополнительные сведения см. в разделе функций RFX под [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке классов*. Например, при которых может потребоваться особое использование параметров см. в разделе [набор записей: получения сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a>Типы данных RFX  
 Библиотека классов предоставляет функции RFX для обмена данными различных типов между источником данных и набором записей. В следующем списке перечислены функции RFX по типу данных. В случаях, необходимо написать собственные функции RFX выберите один из этих функций по типам данных.  
  
|Функция|Тип данных|  
|--------------|---------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  

 Дополнительные сведения см. в документации функции RFX под [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке классов*. Сведения о сопоставлении типов данных C++ типов данных SQL см. в таблице ANSI SQL данные типы сопоставлены типы данных C++ в [SQL: SQL и типы данных C++ (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [Обмен полями записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Набор записей: Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset-класс](../../mfc/reference/crecordset-class.md)   
 [Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)