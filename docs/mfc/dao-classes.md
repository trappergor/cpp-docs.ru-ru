---
title: Классы DAO
ms.date: 09/17/2019
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: febd20971fd85275bd7ded0d2216fab0e05adbd1
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095612"
---
# <a name="dao-classes"></a>Классы DAO

DAO используется с базами данных Access и поддерживается в Office 2013. 3,6 является окончательной версией и считается устаревшей.

Эти классы работают с другими классами платформы приложений, чтобы обеспечить легкий доступ к базам данных объектов DAO, которые используют то же ядро СУБД, что и Microsoft Visual Basic и Microsoft Access. Классы DAO также могут получать доступ к различным базам данных, для которых доступны драйверы ODBC.

Программы, использующие базы данных DAO, имеют по крайней мере `CDaoDatabase` объект `CDaoRecordset` и объект.

> [!NOTE]
>  Визуальная C++ среда и мастера больше не поддерживают DAO (хотя классы DAO включены и их все еще можно использовать). Корпорация Майкрософт рекомендует использовать ODBC для новых проектов MFC. DAO следует использовать только для поддержки существующих приложений.

[кдаоворкспаце](../mfc/reference/cdaoworkspace-class.md)<br/>
Управляет именованным сеансом базы данных, защищенным паролем, от имени входа для выхода из системы. Большинство программ используют рабочую область по умолчанию.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Подключение к базе данных, с помощью которой можно выполнять операции с данными.

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Представляет набор записей, выбранных из источника данных.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Представление, которое отображает записи базы данных в элементах управления.

[кдаокуеридеф](../mfc/reference/cdaoquerydef-class.md)<br/>
Представляет определение запроса (обычно оно сохраняется в базе данных).

[кдаотабледеф](../mfc/reference/cdaotabledef-class.md)<br/>
Представляет хранимое определение базовой или подключенной таблицы.

[кдаоексцептион](../mfc/reference/cdaoexception-class.md)<br/>
Представляет условие исключения, возникающее в классах DAO.

[кдаофиелдексчанже](../mfc/reference/cdaofieldexchange-class.md)<br/>
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO. Как правило, этот класс не используется напрямую.

## <a name="related-classes"></a>Связанные классы

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Инкапсулирует маркер хранения для большого двоичного объекта (BLOB), например точечный рисунок. `CLongBinary`объекты используются для управления большими объектами данных, хранящимися в таблицах базы данных.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Оболочка для **денежного**типа OLE-автоматизации, арифметический тип с фиксированной запятой и 15 цифр перед десятичной запятой и 4 цифры после.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Оболочка для **даты**типа OLE-автоматизации. Представляет значения даты и времени.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Оболочка для типа **Variant**OLE Automation Type. Данные в **варианте Variant**s могут храниться во многих форматах.

## <a name="see-also"></a>См. также

[Обзор класса](../mfc/class-library-overview.md)
