---
title: Классы DAO
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 51abd29ef4de5d70f4a5b2b6b14b53510e7876a1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615935"
---
# <a name="dao-classes"></a>Классы DAO

DAO используется с базами данных Access и поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей.

Эти классы работают с другими классами платформы приложений, чтобы обеспечить легкий доступ к базам данных объектов DAO, которые используют то же ядро СУБД, что и Microsoft Visual Basic и Microsoft Access. Классы DAO также могут получать доступ к различным базам данных, для которых доступны драйверы ODBC.

Программы, использующие базы данных DAO, имеют по крайней мере `CDaoDatabase` объект и `CDaoRecordset` объект.

> [!NOTE]
> Среда и мастера Visual C++ больше не поддерживают DAO (хотя классы DAO включены и их все еще можно использовать). Корпорация Майкрософт рекомендует использовать ODBC для новых проектов MFC. DAO следует использовать только для поддержки существующих приложений.

[CDaoWorkspace](reference/cdaoworkspace-class.md)<br/>
Управляет именованным сеансом базы данных, защищенным паролем, от имени входа для выхода из системы. Большинство программ используют рабочую область по умолчанию.

[CDaoDatabase](reference/cdaodatabase-class.md)<br/>
Подключение к базе данных, с помощью которой можно выполнять операции с данными.

[CDaoRecordset](reference/cdaorecordset-class.md)<br/>
Представляет набор записей, выбранных из источника данных.

[CDaoRecordView](reference/cdaorecordview-class.md)<br/>
Представление, которое отображает записи базы данных в элементах управления.

[CDaoQueryDef](reference/cdaoquerydef-class.md)<br/>
Представляет определение запроса (обычно оно сохраняется в базе данных).

[CDaoTableDef](reference/cdaotabledef-class.md)<br/>
Представляет хранимое определение базовой или подключенной таблицы.

[CDaoException](reference/cdaoexception-class.md)<br/>
Представляет условие исключения, возникающее в классах DAO.

[CDaoFieldExchange](reference/cdaofieldexchange-class.md)<br/>
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO. Как правило, этот класс не используется напрямую.

## <a name="related-classes"></a>Связанные классы

[CLongBinary](reference/clongbinary-class.md)<br/>
Инкапсулирует маркер хранения для большого двоичного объекта (BLOB), например точечный рисунок. `CLongBinary`объекты используются для управления большими объектами данных, хранящимися в таблицах базы данных.

[COleCurrency](reference/colecurrency-class.md)<br/>
Оболочка для **денежного**типа OLE-автоматизации, арифметический тип с фиксированной запятой и 15 цифр перед десятичной запятой и 4 цифры после.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Оболочка для **даты**типа OLE-автоматизации. Представляет значения даты и времени.

[COleVariant](reference/colevariant-class.md)<br/>
Оболочка для типа **Variant**OLE Automation Type. Данные в **варианте Variant**s могут храниться во многих форматах.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
