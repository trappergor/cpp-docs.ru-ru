---
title: Классы DAO | Документация Майкрософт
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
ms.openlocfilehash: c5af80f7a264a15f24ced0be37102802771dc6f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416686"
---
# <a name="dao-classes"></a>Классы DAO

Эти классы работают с другими классами framework в приложения, чтобы предоставить простой доступ к базам данных объекта доступа к данным (DAO), которые используют один и тот же механизм базы данных, как Microsoft Visual Basic и Microsoft Access. Кроме того, классы DAO доступны самые разнообразные баз данных, для которых доступны драйверы Open Database Connectivity (ODBC).

Программы, использующие баз данных DAO будет иметь по крайней мере `CDaoDatabase` объекта и `CDaoRecordset` объекта.

> [!NOTE]
>  Среды Visual C++ и мастерах больше не поддерживают DAO (хотя классы DAO включены и их по-прежнему можно использовать). Корпорация Майкрософт рекомендует использовать для новых проектов MFC ODBC. DAO следует использовать только для поддержки существующих приложений.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Управляет сеансу именованный, защищенной паролем базы данных из имени входа для выхода из системы. Большинство программ использовать рабочую область по умолчанию.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Подключение к базе данных, через который вы можете работать с данными.

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Представляет набор записей, выбранных из источника данных.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Представление, которое отображает записи базы данных в элементах управления.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
Представляет определение запроса, обычно планом, сохраненным в базе данных.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
Представляет хранимое определение базовой или подключенной таблицы.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Представляет условие исключения, поступающее от классов DAO.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO. Этот класс обычно не будет использовать напрямую.

## <a name="related-classes"></a>Связанные классы

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Инкапсулирует маркер в хранилище для больших двоичных объектов (BLOB), например точечный рисунок. `CLongBinary` объекты используются для управления объектами больших объемов данных, хранящихся в таблицах базы данных.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Оболочка для типа автоматизации OLE **валюты**, с фиксированной запятой арифметический тип, с 15 цифр перед десятичной запятой и 4 цифры после.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Оболочка для типа автоматизации OLE **даты**. Представляет значения даты и времени.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Оболочка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться в нескольких форматах.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

