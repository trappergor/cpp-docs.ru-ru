---
title: Классы DAO | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43595ca5f688372a70999231ceebec5282cd3b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dao-classes"></a>Классы DAO
Эти классы работают с другими классами framework приложения предоставляют простой доступ к базам данных объекта доступа к данным (DAO), которые используют один и тот же механизм базы данных, как Microsoft Visual Basic и Microsoft Access. Кроме того, классы DAO доступны самые разнообразные баз данных, для которых доступны драйверы Open Database Connectivity (ODBC).  
  
 Программы, которые используют баз данных DAO будет иметь по крайней мере `CDaoDatabase` объекта и `CDaoRecordset` объекта.  
  
> [!NOTE]
>  Среда Visual C++ и мастерах больше не поддерживают DAO (хотя классы DAO включены и их можно по-прежнему использовать). Корпорация Майкрософт рекомендует использование ODBC для новых проектов MFC. DAO следует использовать только для поддержки существующих приложений.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Управление сеансом именованным, защищенным паролем базы данных от входа до выхода из системы. Большинство программ использовать рабочую область по умолчанию.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Подключение к базе данных, через которую могут работать с данными.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Представляет набор записей, выбранных из источника данных.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Представление, которое отображает записи базы данных в элементах управления.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Представляет определение запроса, как правило, сохраненный в базе данных.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Представляет хранимое определение базовой или подключенной таблицы.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Представляет условие исключения, поступающее от классов DAO.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO. Этот класс обычно не будут использовать напрямую.  
  
## <a name="related-classes"></a>Связанные классы  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Инкапсулирует дескриптор для хранения для большого двоичного объекта (BLOB), такие как растровое изображение. `CLongBinary` объекты используются для управления объектами больших объемов данных, хранящихся в таблицах базы данных.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Программа-оболочка для типа автоматизации OLE **валюты**, с фиксированной запятой арифметический тип с 15 цифр перед десятичной запятой и 4 цифры после.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Программа-оболочка для типа автоматизации OLE **даты**. Представляет значения даты и времени.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Программа-оболочка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться в нескольких форматов.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

