---
title: "ODBC и классы баз данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cf4d5dae14a59cc8b4c6d17ff118cdde59c28af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC и классы баз данных
Классы баз данных ODBC библиотеки MFC инкапсулируют вызовы функций ODBC API, которые обычно приходится самостоятельно в члене функции [CDatabase](../../mfc/reference/cdatabase-class.md) и [CRecordset](../../mfc/reference/crecordset-class.md) классы. Например сложные последовательности вызовов ODBC, привязку возвращаемых записей места хранения, обработку ошибок и других операций управляются классами баз данных. В результате используется намного более простой интерфейс класса для обработки записей с использованием объекта набора записей.  
  
> [!NOTE]
>  Источники данных ODBC доступны через классы MFC ODBC, как описано в этом разделе, или с помощью классов MFC объекта доступа к данным (DAO).  
  
 Несмотря на то, что классы баз данных инкапсулируют функциональность ODBC, они не имеют взаимно-однозначное сопоставление функций ODBC API. Классы баз данных обеспечивают более высокий уровень абстракции, моделируется после доступа к данным объекты, включенные в Microsoft Access и Microsoft Visual Basic. Дополнительные сведения см. в разделе [ODBC и MFC](../../data/odbc/odbc-and-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)