---
title: ODBC и классы баз данных
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 7c69f49cbe233eb0782fdaa9767ea55f4d04203c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213200"
---
# <a name="odbc-and-the-database-classes"></a>ODBC и классы баз данных

Классы базы данных MFC ODBC инкапсулируют вызовы функций API ODBC, которые обычно делают себя в функциях-членах классов [CDatabase](../../mfc/reference/cdatabase-class.md) и [CRecordset](../../mfc/reference/crecordset-class.md) . Например, сложные последовательности вызовов ODBC, привязка возвращаемых записей к местам хранения, обработка условий ошибок и другие операции управляются классами базы данных. В результате вы используете значительно более простой интерфейс класса для управления записями с помощью объекта набора записей.

> [!NOTE]
>  Источники данных ODBC доступны через классы ODBC MFC, как описано в этом разделе, или через классы объектов доступа к данным MFC (DAO).

Несмотря на то что классы базы данных инкапсулируют функциональность ODBC, они не предоставляют однозначного сопоставления функций API ODBC. Классы баз данных обеспечивают более высокий уровень абстракции, смоделированный после обнаружения объектов доступа к данным в Microsoft Access и Microsoft Visual Basic. Дополнительные сведения см. в разделе [ODBC и MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>См. также раздел

[Основы ODBC](../../data/odbc/odbc-basics.md)
