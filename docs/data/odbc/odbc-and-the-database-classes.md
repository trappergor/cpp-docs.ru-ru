---
title: ODBC и классы баз данных
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 709608098a0c979cd7816ae4f8012372099ef52d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575608"
---
# <a name="odbc-and-the-database-classes"></a>ODBC и классы баз данных

Классы баз данных MFC ODBC инкапсулировать вызовы функций ODBC API, которые обычно приходится самостоятельно в члене функции [CDatabase](../../mfc/reference/cdatabase-class.md) и [CRecordset](../../mfc/reference/crecordset-class.md) классы. Например сложные последовательности вызовов ODBC, привязку возвращаемых записей места хранения, обработку ошибок и другие операции являются управляемыми классами баз данных. Таким образом использовании намного более простой интерфейс класса для обработки записей с использованием объекта набора записей.

> [!NOTE]
>  Источники данных ODBC доступны через классы MFC ODBC, как описано в этом разделе, или с помощью классов MFC объекта доступа к данным (DAO).

Несмотря на то, что классы баз данных инкапсулируют функциональность ODBC, они не предоставляют взаимно-однозначное сопоставление функций ODBC API. Классы баз данных обеспечивают более высокий уровень абстракции, на модели доступа к данным объекты, включенные в Microsoft Access и Microsoft Visual Basic. Дополнительные сведения см. в разделе [ODBC и MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>См. также

[Основы ODBC](../../data/odbc/odbc-basics.md)