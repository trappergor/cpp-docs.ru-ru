---
title: Классы DAO
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 7ae85cbeb7790cadb8c26dfbdb7a5163dbcd47c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373517"
---
# <a name="dao-classes"></a>Классы DAO

DAO используется с базами данных Access и поддерживается в Office 2013. DAO 3.6 является окончательной версией, и он считается устаревшим.

Эти классы работают с другими классами платформ приложений, чтобы предоставить легкий доступ к базам данных data Access Object (DAO), которые используют тот же движок базы данных, что и Microsoft Visual Basic и Microsoft Access. Классы DAO также могут получить доступ к широкому спектру баз данных, для которых доступны драйверы Open Database Connectivity (ODBC).

Программы, которые используют базы данных DAO, будут иметь по крайней `CDaoDatabase` мере объект и `CDaoRecordset` объект.

> [!NOTE]
> Среда Visual C и мастера больше не поддерживают DAO (хотя классы DAO включены, и вы все еще можете использовать их). Корпорация Майкрософт рекомендует использовать ODBC для новых проектов MFC. DAO следует использовать только при обслуживании существующих приложений.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Управляет сеансом защищенной паролем базы данных от входа в систему. Большинство программ используют рабочее пространство по умолчанию.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Подключение к базе данных, через которую можно работать на данных.

[Cdaorecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Представляет набор записей, выбранных из источника данных.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Представление, которое отображает записи базы данных в элементах управления.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
Представляет определение запроса, обычно сохраненное в базе данных.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
Представляет хранимое определение базовой или подключенной таблицы.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Представляет условие исключения, возникающее из классов DAO.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO. Обычно вы не будете непосредственно использовать этот класс.

## <a name="related-classes"></a>Похожие классы

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Инкапсулирует ручку для хранения для двоичного крупного объекта (BLOB), например битовой карты. `CLongBinary`объекты используются для управления крупными объектами данных, хранящимися в таблицах баз данных.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Обертка для типа автоматизации OLE **CURRENCY**, арифметического типа с фиксированной точкой, с 15 цифрами до десятичной точки и 4 цифрами после.

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Обертка для типа автоматизации OLE **DATE**. Представляет значения даты и времени.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Обертка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться во многих форматах.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../mfc/class-library-overview.md)
